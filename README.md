# -NginxProxyManager
 NginxProxyManager Setup


---

# 🚀 Nginx Proxy Manager Deployment Guide

## 1. Install Docker
```bash
sudo su
sudo apt update
sudo apt install ca-certificates curl -y
```

### Add Docker’s official GPG key
```bash
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### Add Docker repository
```bash
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/debian
Suites: $(. /etc/os-release && echo "$VERSION_CODENAME")
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF
```

### Install Docker
```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

### Add user to Docker group
```bash
sudo usermod -aG docker $USER
logout
```

---

## 2. Verify Docker Installation
```bash
docker ps -a
```

---

## 3. Clone Nginx Proxy Manager Project
```bash
git clone https://github.com/BoroloxCom/nginxproxymanager-dc.git
cd nginxproxymanager-dc/
```

---

## 4. Configure Docker Compose
Edit the `docker-compose.yml` file if needed:
```bash
nano docker-compose.yml
```

---

## 5. Deploy Nginx Proxy Manager
```bash
docker compose pull
docker compose up -d
```

Check running containers:
```bash
docker ps -a
```

---

## 6. Restart / Re-deploy (if needed)
```bash
sudo -i
cd nginxproxymanager-dc/
docker compose pull
docker compose up -d
exit
```

---

## ✅ Access Nginx Proxy Manager
Once containers are running, open your browser and go to:

```
http://<your-server-ip>:81
```

Default login:
- **Email:** `admin@example.com`
- **Password:** `changeme`



Would you like me to also add a **section on persistent data volumes** so your Nginx Proxy Manager settings survive container restarts?

