# Project Title
CRUD Web Application with Node.js - CI/CD with GitHub Actions
https://crudapp-2.azurewebsites.net/

## Description
This repository contains a web application developed using Node.js and deployed on Azure App Service, which supports CRUD operations with a Azuere MySQL database. The project leverages Azure App Service for hosting and managing the application. Additionally, it integrates GitHub Actions for Continuous Integration and Continuous Deployment (CI/CD), automating the build, test, and deployment processes.

## TechStack:
Container Runtime    : Docker
CI/CD                : Github Actions
Resource             : Azure App Services
Database             : Azure MySQL Database Server
Programming Language : Node.js

## Table of Contents
- [Infrastucture Setup](#infrastucturesetup)
- [Aplication](#application)
- [Security](#security)
- [CI/CD](#cicd)
- [Contact](#contact)


## infrastucturesetup
1. Infrastructure Setup
```
a. Azure App Service:
	 -Sign in to Azure Portal
	 -Create an App Service
	 -Subscription: Choose/Create New.
	 -Resource Group: Choose/Create New.
	 -Name: Crudapp-2
	 -Publish: Choose "Container".
	 -Region: EAST US
	 -Click "Review + create" and then "Create".
b. Azure SQL Database:
	 -Go to "SQL Databases" and click "Create".
	 -Fill in the necessary details:
	 -Subscription: Choose/create new subcription
	 -Resource Group: Choose/create new
	 -Database Name: db-gratis
	 -Servername: db-gratis.mysql.database.azure.com
	 -Location: East US.
	 -Click "Review + create" and then "Create".
	 -Configure Firewall Rule: allow appservice ip to connect database
```

## application
2. Application:<br/>
-This Web application build by Node.js and support CRUD and it's containeraized.<br/>
-please check this url : https://crudapp-2.azurewebsites.net/

## security
3. Security:<br/>
-To control inbound/outbond traffic to Database, I already configured firewall to allow appservice to access this Database.<br/>
-Go to Azure Mysql Server --> Settings --> Networking --> Firewall Rule --> fill the appservice ip
## ci/cd
4. CI/CD:<br/>
-Configure Github Action:
```
-Go to Github Repositories --> settings --> Secret and variables
-add and fill this variable:
-Azure_Credentials
-Azure_Webapp_name
-Registry_Username
-Regirstry_Password
-add folder .github/workflows
-add file deploy-to-azure.yml Please check this url : https://github.com/corpusdelicter/crudapp-2/blob/main/.github/workflows/deploy-to-azure.yml

-to get Azure_Credentials please run this command :
 az ad sp create-for-rbac --name "yourapp" --role contributor --scopes /subscriptions/subscriptionID/resourceGroups/resourcegroupID --sdk-auth
```
## contact
if you have any feedback/concern please kindly send email to: umbudata@gmail.com