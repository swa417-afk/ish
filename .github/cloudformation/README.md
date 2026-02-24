# CloudFormation templates

The files in this directory are **YAML templates**, not shell commands.

To deploy the GitHub OIDC role template:

```bash
aws cloudformation deploy \
  --template-file .github/cloudformation/github-actions-oidc-ecr-role.yml \
  --stack-name astrid-github-oidc-ecr-role \
  --capabilities CAPABILITY_NAMED_IAM \
  --parameter-overrides \
    AwsAccountId=123456789012 \
    GitHubOrgOrUser=your-github-user-or-org \
    GitHubRepository=astrid
```

If you only want to validate the template:

```bash
aws cloudformation validate-template \
  --template-body file://.github/cloudformation/github-actions-oidc-ecr-role.yml
```
