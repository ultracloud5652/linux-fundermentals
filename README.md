# linux-fundermentals

#### Linux is an open-source, Unix-like operating system that powers everything from smartphones and servers to embedded systems and supercomputers. It's popular for its stability, security, and flexibility.

#### There are many Linux distributions (distros) tailored to different use cases:

- Ubuntu (Debian-based): User-friendly, widely used for desktops and cloud servers.

- Debian: Stable and secure, known for strict free software policies.

- CentOS / Rocky Linux (Red Hat-based): Popular in enterprise environments.

- Fedora: Bleeding-edge features, often used by developers.

#### I am using Ubuntu, which uses the apt package manager and is well-suited for beginners and advanced users alike.


## Step 1: Launch an Ubuntu EC2 Instance

#### Sign in to the AWS Management Console.

#### Navigate to EC2 Dashboard (search "EC2" in the top search bar).

#### Click Launch Instance.

#### Configure:

- Name: linux-fundamentals-server

- AMI: Choose “Ubuntu Server 24.04 LTS (Free tier eligible)”

- Instance Type: t2.micro (Free tier eligible)

- Key Pair: Create new (e.g., ubuntu-key) and download the .pem file. Save it securely!

- Network Settings: Allow SSH (port 22) from your IP.

#### Click Launch Instance.**

<img width="969" alt="Screenshot 2025-04-23 at 11 50 26 PM" src="https://github.com/user-attachments/assets/403f4150-6502-4f9f-b281-a4a32a7ff861" />

<img width="996" alt="Screenshot 2025-04-23 at 11 52 40 PM" src="https://github.com/user-attachments/assets/0afbe65a-9480-48ec-8ecf-cdcb78314ab8" />


## Step 2: Connect to Your EC2 via SSH

1. Open your terminal.

2. Navigate to the folder where the .pem file is saved.

3. Set proper permissions:
```bash
   chmod 400 ubuntu-key.pem
```

<img width="981" alt="Screenshot 2025-04-24 at 12 04 01 AM" src="https://github.com/user-attachments/assets/f145804c-1b95-4de9-96ff-c155782650aa" />

4. Connect using:

```bash
ssh -i "ubuntu-key.pem" ubuntu@<your-ec2-public-ip>
```

#### Replace <your-ec2-public-ip> with the public IPv4 address found on your EC2 instance details page.

<img width="925" alt="Screenshot 2025-04-23 at 11 56 23 PM" src="https://github.com/user-attachments/assets/5b12d8e2-9a2f-40bd-8d6a-63bce7c31c74" />


## Step 3: Update the System

#### Always start with updating the package list:

```bash
sudo apt update
```

#### To also upgrade the installed packages:

```bash
sudo apt upgrade
```

<img width="1008" alt="Screenshot 2025-04-23 at 11 57 16 PM" src="https://github.com/user-attachments/assets/83e2b930-404e-415b-adc0-6c004c505753" />

## Step 4: Install the tree Command
#### `tree` shows directory structures in a tree-like format.

#### Install it with:

```
sudo apt install tree
```

<img width="1016" alt="Screenshot 2025-04-23 at 11 58 07 PM" src="https://github.com/user-attachments/assets/a197dbbc-190f-4cc7-92e8-c2765718484a" />

#### Use it like this:

```bash
tree
```

<img width="867" alt="Screenshot 2025-04-24 at 12 46 27 AM" src="https://github.com/user-attachments/assets/b7e6718b-c184-4c7a-a482-12a7d2d4a7cd" />

#### To remove ``tree`` package, run the command:

```
sudo apt remove tree
```


<img width="868" alt="Screenshot 2025-04-24 at 12 01 06 AM" src="https://github.com/user-attachments/assets/e1ae7a25-d590-406d-8905-3e32493e8dcd" />


## Step 5: Install a Web Server (nginx)

#### This is useful for learning how services run on Linux.

Install nginx:

```
sudo apt install nginx -y
```

<img width="1052" alt="Screenshot 2025-04-24 at 12 01 42 AM" src="https://github.com/user-attachments/assets/18735655-84aa-4ec2-8861-e8a2634ccac2" />

#### Check its status:
```
sudo systemctl status nginx
```

<img width="1049" alt="Screenshot 2025-04-24 at 12 53 10 AM" src="https://github.com/user-attachments/assets/8a3f4da2-9dbd-4c4e-a4e2-4f1ed3e03e1e" />

#### To remove the nginx package:

```
sudo apt remove nginx
```

<img width="759" alt="Screenshot 2025-04-24 at 12 03 24 AM" src="https://github.com/user-attachments/assets/34c81509-46be-48eb-9c6a-fe397205f90c" />


