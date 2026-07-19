# AWS Critical Thinking Project: Cloud Storage Solutions and Amazon S3

## Student Information

- **Name:** Samuel Adesanya
- **Course:** AWS Critical Thinking
- **Project:** Cloud Storage Solutions and Amazon S3

---

# Introduction

Cloud storage allows organizations to store and access data over the internet instead of relying on local storage devices or on-premises servers. Amazon Simple Storage Service (Amazon S3) is one of the most popular cloud storage services because it provides secure, highly durable, scalable, and cost-effective object storage for businesses of all sizes.

This project explores Amazon S3, its features, best practices, practical implementation, and disaster recovery planning.

---

# 1. Types of Cloud Storage

Cloud storage can be divided into three major types.

## Block Storage

Block storage stores data in fixed-size blocks. Each block acts like a separate hard drive and is commonly used by operating systems and databases.

Examples:
- Amazon EBS
- Azure Managed Disks

Advantages:
- High performance
- Low latency
- Ideal for databases

---

## File Storage

File storage organizes information into folders and files.

Examples:
- Amazon EFS
- Amazon FSx

Advantages:
- Easy file sharing
- Supports multiple users
- Suitable for shared documents

---

## Object Storage

Object storage stores data as objects instead of files or blocks. Every object contains the actual data, metadata, and a unique identifier.

Examples:
- Amazon S3
- Google Cloud Storage
- Azure Blob Storage

Amazon S3 is an **Object Storage** service.

---

# 2. Key Features of Amazon S3

Amazon S3 offers several important features.

## Durability

Amazon S3 provides **99.999999999% (11 nines)** durability by storing multiple copies of objects across multiple Availability Zones.

## Availability

Amazon S3 offers high availability, allowing users to access their data whenever needed.

## Scalability

Amazon S3 automatically scales to store virtually unlimited amounts of data without manual intervention.

## Security

Amazon S3 protects data through:

- Server-side encryption
- Bucket policies
- IAM permissions
- Access Control Lists (ACLs)
- Versioning
- MFA Delete (optional)

---

# 3. Amazon S3 vs Google Cloud Storage vs Microsoft Azure Blob Storage

| Feature | Amazon S3 | Google Cloud Storage | Azure Blob Storage |
|----------|-----------|----------------------|--------------------|
| Storage Type | Object | Object | Object |
| Durability | 11 Nines | 11 Nines | 11 Nines |
| Integration | AWS Services | Google Cloud | Microsoft Azure |
| CDN | CloudFront | Cloud CDN | Azure CDN |
| Identity Management | IAM | Cloud IAM | Azure Active Directory |
| Lifecycle Policies | Yes | Yes | Yes |

Amazon S3 is widely adopted because of its mature ecosystem and seamless integration with AWS services.

---

# 4. Benefits of Amazon S3

Amazon S3 provides several benefits.

- Highly scalable
- Cost-effective
- Easy to manage
- Highly durable
- Secure
- Flexible storage classes
- Supports static website hosting
- Supports backup and disaster recovery

---

# 5. Integration with AWS Services

Amazon S3 integrates with several AWS services.

## IAM

IAM controls who can access S3 buckets and objects.

## Bucket Policies

Bucket policies define permissions for users, accounts, and services.

## Amazon EC2

Applications running on EC2 can store and retrieve files directly from S3.

## Amazon CloudFront

CloudFront delivers S3 content globally with low latency using edge locations.

## AWS Lambda

Lambda automatically processes files uploaded into S3.

Example:
- Resize uploaded images
- Generate thumbnails
- Process documents

---

# 6. Best Practices for Amazon S3

Recommended best practices include:

- Enable bucket versioning.
- Enable server-side encryption.
- Block public access.
- Use IAM roles instead of root credentials.
- Apply the principle of least privilege.
- Enable lifecycle rules.
- Monitor bucket activity using CloudTrail.
- Enable logging.
- Regularly review permissions.

---

# Practical Implementation

The following tasks were completed in AWS.

---

## Step 1: Create an S3 Bucket

A new Amazon S3 bucket was created in the AWS Management Console.

**Screenshot**

<img width="2560" height="1440" alt="Screenshot 2026-07-16 104243" src="https://github.com/user-attachments/assets/7170fab7-87af-47a0-9369-fc1d1ee49eef" />

<img width="2560" height="1440" alt="Screenshot 2026-07-16 104205" src="https://github.com/user-attachments/assets/d612d8dd-4afd-4868-a84e-350b17e4c11d" />

<img width="2560" height="1440" alt="Screenshot 2026-07-16 104105" src="https://github.com/user-attachments/assets/bda1ca07-dac4-42a6-9b97-940771c0f0da" />

<img width="2560" height="1440" alt="Screenshot 2026-07-16 104034" src="https://github.com/user-attachments/assets/14011219-5d26-41b6-836e-f9da123f9f88" />

<img width="2560" height="1440" alt="Screenshot 2026-07-16 104009" src="https://github.com/user-attachments/assets/45ea34bd-fc5c-4e4f-93e9-5b15cdf1c8a1" />

---

## Step 2: Bucket Successfully Created

The bucket was successfully created.

**Screenshot**

<img width="2560" height="1440" alt="Screenshot 2026-07-16 104243" src="https://github.com/user-attachments/assets/7207fb2c-e5aa-4d89-8156-a39c0bf1ca7c" />

---

## Step 3: Upload Files

Several files were uploaded into the bucket.

**Screenshot**

<img width="2560" height="1440" alt="Screenshot 2026-07-19 131952" src="https://github.com/user-attachments/assets/c88e9e63-4c20-43ca-9c73-b26f8f225ab6" />

---

## Step 4: Folder Structure

Folders were created to organize the objects.

**Screenshot**

<img width="2502" height="265" alt="Screenshot 2026-07-19 131951" src="https://github.com/user-attachments/assets/7ef4046f-3bc1-44d9-8cbb-225d2af69ced" />

---

## Step 5: Bucket Versioning

Bucket versioning was enabled to preserve previous versions of uploaded files.

Benefits include:

- Accidental deletion recovery
- Object restoration
- Improved disaster recovery

**Screenshot**

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/a56f9e00-3dfb-49f4-a82c-67109e27b45e" />

---

## Step 6: Default Encryption

Server-side encryption (SSE-S3) was enabled to automatically encrypt uploaded objects.

**Screenshot**

<img width="2080" height="446" alt="image" src="https://github.com/user-attachments/assets/ae4571d5-e8dd-45e0-b3fc-b2566df3ca14" />

---

## Step 7: Permissions

The following security settings were configured.

- Block Public Access enabled
- ACLs disabled
- Bucket Owner Enforced

**Screenshot**

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/68f1a7ff-902a-4435-9444-940ff6e9bf07" />

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/cf20d360-b7f6-4236-a6b9-b78e16350968" />

---

## Step 8: Lifecycle Rule

A lifecycle policy was created to automatically transition older files into lower-cost storage.

Benefits include:

- Reduced storage costs
- Automatic archive management

**Screenshot**

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/a57ffaaf-9079-4a2a-92d3-694a031dd745" />

---

## Step 9: Bucket Overview

The final bucket configuration is shown below.

**Screenshot**

<img width="2560" height="1440" alt="Screenshot 2026-07-19 131952" src="https://github.com/user-attachments/assets/ffa94099-61ba-4a76-ab6d-d8b0f97393eb" />

---

# Storage Solution for a Large E-Commerce Website

An e-commerce website stores thousands of product images, promotional videos, and downloadable files. Storing these assets directly on web servers can reduce performance and make scaling difficult.

## Recommended Solution

The recommended solution is to use Amazon S3 as the primary object storage service and Amazon CloudFront as the content delivery network (CDN).

### Benefits

- Unlimited scalability
- High availability
- Faster global content delivery
- Lower server workload
- Reduced storage costs using Intelligent-Tiering and Lifecycle Rules
- Easy integration with EC2 and Lambda

This architecture improves website performance while reducing operational costs.

---

# Security Strategy for 30 Internal Videos

To protect confidential company videos stored in Amazon S3, the following security measures should be implemented.

## Encryption

- Enable Server-Side Encryption (SSE-S3)
- Encrypt all uploaded videos automatically

## Access Control

- Block all public access
- Use IAM roles
- Apply least privilege permissions
- Restrict bucket policies

## Monitoring

- Enable AWS CloudTrail
- Enable S3 access logging
- Monitor with Amazon CloudWatch
- Configure security alerts

## Data Protection

- Enable Versioning
- Enable MFA for administrators
- Perform regular security audits

These controls help ensure that only authorized users can access the videos while maintaining data integrity and confidentiality.

---

# Disaster Recovery Plan

To ensure business continuity during disasters, the following strategy should be implemented.

## Data Backup

- Store data in Amazon S3
- Enable Versioning
- Schedule regular backups

## Redundancy

- Store copies across multiple Availability Zones
- Enable Cross-Region Replication for critical data

## Failover

- Use Route 53 health checks
- Deploy applications across multiple Availability Zones

## Recovery

If a disaster occurs:

1. Assess the incident.
2. Recover application infrastructure.
3. Restore data from S3.
4. Verify application functionality.
5. Resume normal operations.

This approach minimizes downtime and reduces the risk of data loss.

---

# Conclusion

Amazon S3 provides a secure, scalable, and cost-effective object storage solution for businesses of all sizes. Its integration with other AWS services, strong security features, lifecycle management, and disaster recovery capabilities make it an ideal platform for modern cloud applications.

Through this project, I gained practical experience creating and managing Amazon S3 buckets, configuring security settings, enabling versioning, applying encryption, and implementing lifecycle management while understanding how Amazon S3 supports enterprise cloud storage solutions.
