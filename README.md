# AWS Three-Tier Web Application Infrastructure

## Overview
Infrastructure as Code (IaC) implementation of a scalable, secure three-tier web architecture on AWS. This architecture supports a web application with separated presentation, application, and data layers for optimal security and scalability.

Goals: 
- Deployed via IaC (Terraform)
- Setup VPCs
- ECS for container orchestration
- Load balancers and scaling groups
- IAM Roles and Security Groups 
- Deploy via CI/CD

## Architecture

![Architecture Diagram (Coming Soon)]()

### Infrastructure Components

#### Network Layer
- VPC with multi-AZ deployment
- Public and private subnets
- NAT Gateways for private subnet access
- Internet Gateway for public access

#### Application Tiers

1. **Web Tier (Public)**
   - Application Load Balancer
   - Web servers in Auto Scaling Group
   - Static content delivery

2. **Application Tier (Private)**
   - Application servers in private subnets
   - Auto Scaling Group for dynamic workloads
   - Service-to-service communication

3. **Database Tier (Private)**
   - Managed database service
   - Data replication across AZs
   - Backup and recovery systems

## Infrastructure Layout

## Network Flow 
Internet → ALB (Public Subnet) → Application Containers (Private Subnet)


  Internet  →    Public Subnet    →   Private Subnet   
                  (Web Tier)            (App Tier)      

                     ALB                Containers 


                  NAT Gateway   
              