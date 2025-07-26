# Techeazy DevOps Assignments

## Assignment 1 – Automate EC2 Deployment

This assignment involved deploying a Java-based Spring Boot application to an EC2 instance, automating the entire process from code to deployment.

### Steps Completed:

1. **Launch EC2 Instance**:
   - OS: Amazon Linux 2023
   - Instance type: t2.micro
   - Security Group: Allowed HTTP (port 80) and SSH (port 22)

2. **Connect EC2 via MobaXterm**

3. **Install Java**:
   - Installed Amazon Corretto 21
   - Verified using `java -version`

4. **Clone Spring Boot Repo**:
   - Repo: `https://github.com/Trainings-TechEazy/test-repo-for-devops`
   - Command: `git clone <repo-url>`

5. **Build Project Using Maven**:
   - Installed Maven
   - Ran `mvn clean install`
   - Verified WAR/JAR in `target` folder

6. **Run Application**:
   - Used `nohup java -jar <filename>.jar &`
   - Application running on **port 80**

7. **Verify**:
   - Application accessible via EC2 Public IP on port 80
   - Logs verified using `tail -f nohup.out`

---

## Assignment 2 – S3 Upload with Lifecycle Rule

This assignment required uploading application logs to an S3 bucket with proper IAM roles and applying a lifecycle policy.

### Steps Completed:

1. **Created S3 Bucket**:
   - Bucket name: `devops-logs-s3-buc`
   - Folder structure: `app-logs/`

2. **Created IAM Policy and Role**:
   - Created a custom policy with `s3:PutObject`, `s3:CreateBucket`
   - Attached it to EC2 role for S3 write access

3. **Installed AWS CLI on EC2**

4. **Configured AWS CLI on EC2**:
   - Ran `aws configure` with IAM credentials

5. **Uploaded Logs**:
   - Copied logs using:
     ```
     aws s3 cp /path/to/app/logs.log s3://devops-logs-s3-buc/app-logs/
     ```

6. **Verified Upload**:
   - Checked logs in S3 from AWS Console

7. **Lifecycle Rule**:
   - Created a rule named `delete-after-7-days`
   - All objects in `app-logs/` are set to delete after 7 days

---

##  File Structure
├── README.md ├── assignment1.txt └── assignment2.txt (submitted via PR)

## Important Links

-  GitHub Repository: [https://github.com/vaishnavidabhole/techeazy-ec2-deploy](https://github.com/vaishnavidabhole/techeazy-ec2-deploy)
-  Assignment 2 Pull Request: [PR #1](https://github.com/vaishnavidabhole/techeazy-ec2-deploy/pull/1)

