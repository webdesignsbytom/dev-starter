# Dev Starter

This file will cover information about
Devops / AWS / Hosting / SSL

Including information about signing up, best practices, types of service and general data

## Azure Devops

Azure is the Microsoft service portal for ioT and Saas and other services.
The main one of interest to me is Devops

### Account Info

Create and account through microsoft.
Your account structure will look like this: - Root (login user) - Organization (organization name i.e webdesignsbytom) - Projects - Repo for code - Data - Boards - Pipeline - Test Plan - Artifcats

### API

The general API will look like this and have components
GET {instanceURL}/

How to access the REST API 

1. Create a personal access token
2. Go to project settings and create PAT
3. Use the pat code as a header to request access



## Amazon Web Services

AWS host many services you may want to rent or buy on demand.

### IAM

Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources.
DO NOT use root level access.

Secure individaual and group control
Fine grain access options

Use case!
User must be logged in to access AWS and can iterface using:

1. SKD
2. AWS CLI
3. API and management console

POLICY: a JSON doc that set out user permissions
IAM policys have action values that.

How to use.

1. Create a IAM group for each department
2. Each group has its own policy for users to inherit.
3. Create IAM users

You can temporarily add Admin Role Policy to users without having to change their current role.
Most users can have access 'Power User' role

### EC2

To sign up for an EC2 instance you must first

1. sing up to aws
2. Create an admin user
   1. Sign in as root user
   2. Turn on multi-factor authentication (MFA) for your root user.
3. Create a key pair
4. Create a security group.

Create a Server

1. Click Launch Instance
2. Select Server VM
3. Go to advanced and 'Create IAM Profile'
4. Click 'Create Role' and select the ec2 option
5. Add permsiions for SSM (Simple Systems Manager) - way to log into machine
6. Then create
7. Go back to the Server creation form and for IAM instance profile - select the new role
8. You will be asked to create a 'Key Pair' we dont need to do this with ssm
9. Launch instance

Managing A server

3 Options SSH, VM or Session Manager

1. Session Manager

- Go to Systems Manager and find the tab Sessions manager
- Click start a session
- Select the target instance and click start session to be taken to a CLI page.
- It logs you in as the root user so you must swap to the IAM user
- `sudo su - ec2-user`

### AMI

And AMI is creating an Image of your whole server to save it.

1. On an instance, click on 'Actions' Go to the images tab and click 'Create Image'
2. Give it an name and desc and then leae all settings as stardard and create.
3. They are then stored in the list of AMI's and can be used to create a server from the image.
