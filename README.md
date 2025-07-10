# Terraform AWS S3 Static Website

This Terraform project provisions an AWS S3 bucket configured as a static website with sample HTML files and an image.

## Features

- Creates a public S3 bucket with website hosting enabled
- Uploads sample files (`index.html`, `error.html`, `profile.jpg`)
- Configures bucket ownership, ACLs, and public access settings
- Sets up website configuration with index and error documents

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) (>= 1.0.0)
- [AWS CLI](https://aws.amazon.com/cli/) configured with credentials
- AWS account with S3 permissions

## Architecture

![Architecture Diagram](https://via.placeholder.com/600x400?text=S3+Static+Website+Architecture)

## Usage

### 1. Clone the repository (if applicable)

```bash
git clone https://github.com/your-repo/terraform-s3-website.git
cd terraform-s3-website


2. Initialize Terraform
bash
terraform init
3. Review execution plan
bash
terraform plan -var="bucket_name=your-unique-bucket-name"
4. Apply configuration
bash
terraform apply -var="bucket_name=your-unique-bucket-name"
5. Access your website
The website URL will be displayed in the output (format: http://<bucket-name>.s3-website-<region>.amazonaws.com)

Input Variables
Name	Description	Type	Default	Required
bucket_name	Unique name for the S3 bucket	string	-	yes
Outputs
Name	Description
website_endpoint	The website endpoint URL
bucket_name	The name of the created S3 bucket
File Structure
text
.
├── main.tf                 # Main Terraform configuration
├── variables.tf            # Variable declarations
├── outputs.tf              # Output definitions
├── index.html              # Website index page
├── error.html              # Website error page
├── profile.jpg             # Sample image file
├── README.md               # This documentation
└── .gitignore              # Git ignore file
Customizing Content
Replace these files with your own content:

index.html - Your main website page

error.html - Custom error page

profile.jpg - Any image file (update the reference in main.tf if changing filename)

Clean Up
To destroy all created resources:

bash
terraform destroy -var="bucket_name=your-bucket-name"
Security Considerations
⚠️ Important Security Notes:

This configuration makes the bucket and its contents publicly readable

For production use:

Consider adding bucket policies for more granular access control

Implement CloudFront with OAI for better security

Enable S3 bucket logging

Set up proper IAM permissions

Troubleshooting
Common Issues
Bucket name already exists: Choose a globally unique name

Access denied errors: Verify your AWS credentials have S3 permissions

Files not updating: Run terraform apply again after file changes

Contributing
Pull requests are welcome. For major changes, please open an issue first.
```
