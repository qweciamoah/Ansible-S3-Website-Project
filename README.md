```markdown
 Ansible S3 Static Website Deployment

This project automates the deployment of a static website (a professional resume) to an AWS S3 bucket using Ansible. It demonstrates core DevOps principles like **Infrastructure as Code (IaC)** and **CI/CD automation**.

 📖 Overview

The repository contains:
*   Static Website Files: HTML and CSS for a professional resume website.
*   Ansible Playbook: Code to provision and configure the AWS S3 infrastructure and deploy the website.
*   GitHub Integration: Version control for the entire project.

With a single command, the Ansible playbook will:
1.  Create a configured S3 bucket.
2.  Apply the correct public read policy.
3.  Enable static website hosting.
4.  Upload all website files.
5.  Output the website URL.

 📁 Project Structure

`
Ansible-S3-Website-Project/ │
   ├── index.html    # Main resume webpage
   ├── error.html    # Custom 404 error page
   ├── style.css     # Stylesheet for the website
   ├── deploy_s3.yml # Ansible playbook for deployment
   └── README.md       

```

 ⚙️ Prerequisites

Before running the playbook, ensure you have the following installed and configured:

1.  Ansible: `pip install ansible`
2.  Ansible AWS Collection: `ansible-galaxy collection install amazon.aws`
3.  AWS CLI:Installed and configured with credentials for an IAM user that has permissions to create and manage S3 buckets.
    ```bash
    aws configure
    AWS Access Key ID [None]: YOUR_ACCESS_KEY
    AWS Secret Access Key [None]: YOUR_SECRET_KEY
    Default region name [None]: us-east-1
    Default output format [None]: json
    ```
4.  Export AWS Credentials: The playbook uses environment variables for security.
    ```bash
    export AWS_ACCESS_KEY_ID='YOUR_ACCESS_KEY'
    export AWS_SECRET_ACCESS_KEY='YOUR_SECRET_KEY'
    ```

## 🚀 Usage

1.  Clone the repository:
    ```bash
    git clone https://github.com/qweciamoah/Ansible-S3-Website-Project.git
    cd Ansible-S3-Website-Project
    ```

2.  Review and customize variables (optional): Edit `deploy_s3.yml` to change the default `bucket_name` or `region`.

3.  Run the Ansible playbook:
    ```bash
    ansible-playbook deploy_s3.yml
    ```

4.  Access your website:After a successful run, the playbook will output the URL of your live website (e.g., `http://your-bucket-name.s3-website-us-east-1.amazonaws.com`).

🔧 The Ansible Playbook (`deploy_s3.yml`)

The playbook performs the following tasks:
Gathering Facts: Collects information about the local host.
Create S3 Bucket: Uses the `amazon.aws.s3_bucket` module to create the bucket.
Apply Public Read Policy: Sets a bucket policy to allow public read access for website hosting.
Enable Website Hosting: Uses the AWS CLI shell command to configure the bucket for static website hosting.
Upload Website Files: Syncs local files to the S3 bucket using the `amazon.aws.s3_sync` module, setting permissions to `public-read`.
Output Website URL: Prints the URL to access the deployed site.

 🛠️ Technologies Used

*   Infrastructure as Code (IaC): Ansible
*   Cloud Provider: AWS (S3, IAM)
*   Version Control: Git, GitHub
*   Frontend: HTML, CSS

📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

👤 Author

Paul Amoah 

DevOps Engineer  
- Email: Amoahpaul580@gmail.com
- LinkedIn:https://www.linkedin.com/in/paul-amoah123
- GitHub: [@qweciamoah](https://github.com/qweciamoah)
