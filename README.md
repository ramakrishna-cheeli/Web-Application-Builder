# Web-Application-Builder
## This Project Mainly focuses on:
- Create an architectural diagram to depict various AWS services and their interactions with each other.
- Estimate the cost of using services by using the AWS Pricing Calculator.
- Deploy a functional web application that runs on a single virtual machine and is backed by a relational database.
- Architect a web application to separate layers of the application, such as the web server and database.
- Create a virtual network that is configured appropriately to host a web application that is publicly accessible and secure.
- Deploy a web application with the load distributed across multiple web servers.
- Configure the appropriate network security settings for the web servers and database.
- Implement high availability and scalability in the deployed solution. 
- Configure access permissions between AWS services.
## Requirements
- **Functional**: The solution meets the functional requirements, such as the ability to view, add, delete, or modify the student records, without any perceivable delay.
- **Load balanced**: The solution can properly balance user traffic to avoid overloaded or underutilized resources.

- **Scalable**: The solution is designed to scale to meet the demands that are placed on the application.

- **Highly available**: The solution is designed to have limited downtime when a web server becomes unavailable.

- **Secure**:
    - The database is secured and can’t be accessed directly from public networks.
    - The web servers and database can be accessed only over the appropriate ports.
    - The web application is accessible over the internet.
    - The database credentials aren’t hardcoded into the web application.
- **Cost optimized**: The solution is designed to keep costs low.

- **High performing**: The routine operations (viewing, adding, deleting, or modifying records) are performed without a perceivable delay under normal, variable, and peak loads.
## Solution Requirements
- The application is deployed in one AWS Region (the solution does not need to be multi-Regional).
- The website does not need to be available over HTTPS or a custom domain.
- The solution is deployed on Ubuntu machines by using the JavaScript code that is provided.
- Use the JavaScript code as written unless the instructions specifically direct you to change the code.
- The solution uses services and features within the restrictions of the lab environment.
- The database is hosted only in a single Availability Zone.
- The website is publicly accessible without authentication.
- Estimation of cost is approximate.
## Solution Phases
### Phase 1: Planning the design and estimating cost
- **Task 1: Creating an architectural diagram**
  - This site provides tools to draw AWS architecture diagrams [Architecture Icons](https://aws.amazon.com/architecture/icons/)
  - This site provides tools to draw AWS architecture diagrams [Architecture Diagrams](https://aws.amazon.com/architecture/reference-architecture-diagrams/?solutions-all.sort-by=item.additionalFields.sortDate&solutions-all.sort-order=desc&whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc&awsf.whitepapers-tech-category=tech-category%23analytics&awsf.whitepapers-industries=*all)
- **Task 2: Developing a cost estimate**
  -  Develop a cost estimate for 12 month in the us-east-1 Region using the Pricing Calculator [AWS Pricing Calculator](https://calculator.aws/#/)
### Phase 2: Creating a basic functional web application
- **Task 1: Creating a virtual network**
  - Create a Virtual Network using the VPC (VPC, Subnets(Public,Private), Internet Gateway, Route Table)
- **Task 2: Creating a virtual machine**
  - Create a virtual machine in the cloud to host the web application.
  - To install the required web application and database on the virtual machine use the file code.sh
- **Task 3: Testing the deployment**
    - Test the deployment of the web application to ensure it is accessible from the internet and functional. Perform a few tasks, such as viewing, adding, deleting, or modifying records.
### Phase 3: Decoupling the application components
- The objective is to separate the database and the web server infrastructure so that they run independently. The web application should run on a separate virtual machine, and the database should run on the managed service infrastructure.
- **Task 1: Changing the VPC configuration**
    - Update or re-create the virtual network components that are necessary to support hosting the database separately from the application.
    - You need private subnets in a minimum of two Availability Zones.
- **Task 2: Creating and configuring the Amazon RDS database**
    - Create an Amazon Relational Database Service (Amazon RDS) database that runs a MySQL engine. You can choose to create a provisioned instance or run it serverlessly.
    - Allow only the web application to access the database.
    - Don't enable enhanced monitoring.
- **Task 3: Configuring the development environment**
    - Provision an AWS Cloud9 environment to run AWS Command Line Interface (AWS CLI) commands in later tasks.
    - Use a t3.micro instance for the AWS Cloud9 environment.
    - Use Secure Shell (SSH) to connect to the environment.[Reference](https://docs.aws.amazon.com/cloud9/latest/user-guide/create-environment-main.html)
- **Task 4: Provisioning Secrets Manager**
    - Use AWS Secrets Manager to create a secret to store the database credentials, and configure the web application to use Secrets Manager.
    - From scripts.yml use the script 1 to create the secretes in the Secretes Manager by using the AWS CLI.
    - [Reference](https://docs.aws.amazon.com/cli/latest/reference/secretsmanager/create-secret.html)
- **Task 5: Provisioning a new instance for the web server**
    - reate a new virtual machine to host the web application.
    - To install the required web application on the virtual machine, use the JavaScript code from the following link:

                              
