# mysql_database_creation_using_AWS_Codebuild
 creating mysql database and a table using AWS codebuild:
 
 - buildspec.yml file has two main stapes:
   1. Creating the RDS mysql database within a predefined VPC and subnet 
   2. Creating a table by connecting to the database and creating the table and add a sample data to the table
   
 - To create RDS mysql database, AWS cli commands were used in buildspec.yml file. therefore, in the setup of the codebuild process, amazon linux image was used where AWS Cli is already installed.
 
 - new role also was created for this specific build project
 
 - In order to create the mysql table, mysql client was installed on the container and mysql client commands were used to connect to the table and create the table
 
 - It is important to mention that as the mysql datbase was needed to be created within a VPC and subnet and then connecting to that database to create the table, codebuild required to have access to that VPC and subnet and therefore, NAT gatway was required to be defined on the private subnet of the VPC. 

https://docs.aws.amazon.com/codebuild/latest/userguide/vpc-support.html

https://aws.amazon.com/blogs/devops/access-resources-in-a-vpc-from-aws-codebuild-builds/
