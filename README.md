# How-to-install-Docker-on-Ubuntu

🛠️ Step 1: Update the System

### Before installing Docker, update the package list
````bash
sudo apt update && sudo apt upgrade -y
````

📥 Step 2: Install Required Dependencies

### Install packages that allow apt to use repositories over HTTPS
````bash
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
````

🌍 Step 3: Add Docker’s Official GPG Key

### Run this command to add Docker’s GPG key:
````bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
````

📌 Step 4: Add Docker Repository

````bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
````

### Now, update the package index
````bash
sudo apt update
````

📌 Step 5: Install Docker

### Install Docker Engine and related packages
````bash
sudo apt install -y docker-ce docker-ce-cli containerd.io
````

🚀 Step 6: Start and Enable Docker
````bash
sudo systemctl start docker
sudo systemctl enable docker
````

🔍 Step 7: Verify Docker Installation
### Check if Docker is installed correctly by running
````bash
docker --version
````
output like:
````bash
Docker version 24.0.5, build 1234567
````
### Test Docker with
````bash
sudo docker run hello-world
````
If everything is set up correctly,  see a success message.

🛠️ Optional: Run Docker Without sudo

### By default, need sudo to run Docker. To run it as a normal user
````bash
sudo usermod -aG docker $USER
````

Then restart  system
````bash
reboot
````
After reboot, check
````bash
docker ps
````
✅ Done!
