# aws-terraform-codespace-environment
A fully automated, zero-install cloud engineering workspace using GitHub Codespaces, pre-configured with the AWS CLI and Terraform.

# AWS & Terraform Codespace Environment ☁️🛠️

A fully automated, cloud-based development environment for AWS and Terraform projects. 

This repository uses a custom `devcontainer.json` configuration to automatically build a sterile, ready-to-use cloud environment directly in your browser.

## ✨ Features
* **Zero-Install Setup:** No local dependencies required. Everything runs securely in the cloud.
* **Base Environment:** Built on Microsoft's official Universal Dev Container (`mcr.microsoft.com/devcontainers/universal:2`), which includes Python, Node.js, and standard dev tools out-of-the-box.
* **AWS CLI (Latest):** Automatically pulls and installs the newest AWS Command Line Interface on every build.
* **Terraform (v1.15.3):** Hardcoded to version 1.15.3 for strict stability during coursework and tutorials.
* **Auto-Cleanup:** Automatically deletes heavy installation files (`.zip` binaries and licenses) to keep the workspace clean and lightweight.

---

## 👯‍♀️ Want to build your own? (How to copy this setup)

If you want to use this automated environment as a starting point for your own AWS or Terraform projects, do not clone this repository directly. Instead, generate your own clean copy!

1. Click the green **Use this template** button at the top right of this repository's GitHub page.
2. Select **Create a new repository**.
3. Name your new repository whatever you'd like and save it to your own GitHub account.
4. Follow the setup instructions below to add your own AWS keys and launch your environment.

*(Note: Creating a repository from this template gives you a completely clean slate with zero commit history, so you are truly starting from scratch!)*

---

## 🚀 How to Use This Environment

### 1. Set Up Your AWS Credentials (Required)
Before launching the Codespace, you must provide your AWS credentials so the CLI can authenticate you securely. **Never commit these keys to your code.**

1. Go to your new repository's **Settings** tab.
2. On the left sidebar, navigate to **Secrets and variables** > **Codespaces**.
3. Add the following **Repository Secrets**:
   * `AWS_ACCESS_KEY_ID`: Your AWS access key.
   * `AWS_SECRET_ACCESS_KEY`: Your AWS secret key.
   * `AWS_DEFAULT_REGION`: Your preferred region (e.g., `us-east-1`).

### 2. Launch the Codespace
1. Click the green **<> Code** button at the top of your repository.
2. Select the **Codespaces** tab.
3. Click **Create codespace on main**.
4. Wait 1-2 minutes for the automated build script to finish installing and configuring your tools.

### 3. Verify the Installation
Once the terminal is ready, run these two commands to verify your environment is fully configured and authenticated:

**Verify AWS Authentication:**
```bash
aws sts get-caller-identity
