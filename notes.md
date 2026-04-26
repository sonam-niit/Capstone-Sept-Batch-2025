# Project Implementation

- clone my repository: https://github.com/sonam-niit/Capstone-Sept-Batch-2025.git
- or else follow below steps:

1. create folder named frontend:
    - inside create index.html
    - add shown code here
2. create folder called backed:
    - create folder generate-presigned-url
        + main.py
    - create folder process-uploaded-file
        + main.py

## Bucket Details

- here we need 3 buckets

1. S3 Remote Backend (create manually)
2. for uploading files (create using terraform)
3. for frontend hosting (create using terraform)

- create bucket run below commands in terminal

```bash
aws s3api create-bucket \
--bucket devops-accelerator-platform-tf-state-sonam \
--region us-east-1
```

- create DynamoDB table for Locking
- remote state locking

```bash
aws dynamodb create-table \
--table-name devops-accelerator-tf-locker \
--attribute-definitions AttributeName=LockID,AttributeType=S \
--key-schema AttributeName=LockID,KeyType=HASH \
--billing-mode PAY_PER_REQUEST \
--region us-east-1
```