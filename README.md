# terraform-aws
Learning to use Terraform on AWS<br>
https://developer.hashicorp.com/terraform/tutorials/aws-get-started


Steps to create an EC2 infra on VPC via HCP terraform workspace for learning purposes with my config files:
1. Create an AWS IAM user and give it AdministratorAccess policy. This will generate access and secret keys (save them somewhere!)
2. Add access and secret keys to your environment:
   ```
   export AWS_ACCESS_KEY_ID=<ACCESS KEY>
   export AWS_SECRET_ACCESS_KEY=<SECRET KEY>
   ```
4. In the HCP terraform platform, create an organization and workspace
6. Now we need to connect the local terraform environment to the remote HCP workspace:
   ```
   terraform login
   ```
7. Type yes to proceed then it will give you a link to put on your browser to create a token (save it somewhere!)
8. Add token to the Value prompt in the terminal
9. Add the AWS access and secret key to your HCP workspace that you created on the HCP terraform platform in the settings as environment variables and mark them as Sensitive
10. Add your organization and workspace names to the relevant variables in the terraform.tf file
5. Change the AWS region to the one closest one to you in the main.tf file
11. Finally run the following commands in the terminal while on the root directory of this project to create the infra on AWS:
   ```
   terraform init
   ```
   ```
   terraform apply
   ```
11. Type yes when prompted
12. Now you have a working EC2 in a VPC on AWS

To destroy the infra just type in the terminal:
```
terraform destroy
```
