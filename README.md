# ansible-project
simple configuration automation using ansible to get the code from the github and  deploy it on the ec2 instance

# Ansible Static Website Deployment

This project uses **Ansible** to automate the deployment of a static website hosted on **GitHub** to an **EC2 instance** running **Ubuntu** and **Nginx**.

## 🧰 Project Structure
├── inventory.ini
├── setup.yml
└── roles/
├── app/
│ └── tasks/main.yml
├── base/
│ └── tasks/main.yml
├── nginx/
│ └── tasks/main.yml
└── ssh/
└── tasks/main.yml


## ⚙️ What It Does

- Installs base packages like Git, Vim, and security tools
- Configures SSH access using a public key
- Installs and configures Nginx
- Clones static site files from GitHub
- Deploys the static site under `/var/www/html`

## 🚀 How to Run

1. **Ensure EC2 instance is running and reachable via SSH**

2. **Update `inventory.ini` with your server details:**

```ini
[webserver]
<your-ec2-ip> ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/your-key.pem

# Run the playbook
ansible-playbook -i inventory.ini setup.yml

# SSH Key
Keep your .pem (private key) file secure and use chmod 400 for correct permissions.

Add the public key to the remote EC2 instance using the ssh role.

📁 GitHub Repo
Make sure your static site is available in a public GitHub repo (or use SSH auth for private repos).
