<p align="center"> <img src="https://www.wiredoor.net/images/wiredoor.svg" alt="Wiredoor logo" width="60" /> </p>

<h1 align="center" style="color:#1c398e">
  Wiredoor
</h1>

<p align="center">
  <strong>Expose private services securely through reverse VPN tunnel powered by WireGuard and NGINX.</strong><br />
  Open-source | Self-hosted
</p>

<p align="center">
  <a href="https://www.wiredoor.net/docs">Documentation</a> •
  <a href="https://github.com/wiredoor/wiredoor">Core Server</a> •
  <a href="https://github.com/wiredoor/wiredoor-cli">CLI</a> •
  <a href="https://charts.wiredoor.net">Helm Charts</a>
</p>

---

# Wiredoor Server Docker Setup

This repository provides a simple, production-ready Docker Compose setup to self-host [**Wiredoor**](https://www.wiredoor.net), a secure, open-source Ingress-as-a-Service platform that exposes internal services to the internet via reverse VPN tunnels powered by [WireGuard](https://www.wireguard.com).

---

## 🚀 Quickstart

### 1. Clone the repository

```bash
git clone https://github.com/wiredoor/docker-setup.git
cd docker-setup
```

### 2. Create and edit .env

```bash
cp .env.example .env
nano .env
```

Make sure to set your **admin credentials** and **VPN hostname** (your server’s public IP or domain).

### 3. Launch Wiredoor

```bash
docker compose up -d
```

## Edit environment variables

To change configuration (admin credentials, VPN port, TCP_SERVICE_PORT_RANGE, etc.), simply edit your `.env` file:

```bash
nano .env
```

After making changes, recreate the container to apply them:

```bash
docker compose up -d wiredoor --force-recreate
```

## Update Wiredoor to the latest version

Wiredoor images are versioned and published to GitHub Container Registry.

To update to the latest available version:

```bash
docker compose pull wiredoor
docker compose up -d wiredoor --force-recreate
```

### Pin specific Wiredoor version

Edit your `docker-compose.yml` like this:

```bash
image: ghcr.io/wiredoor/wiredoor:v1.0.1
```

Then:

```bash
docker compose up -d wiredoor --force-recreate
```

Check for new releases on: [https://github.com/wiredoor/wiredoor/releases](https://github.com/wiredoor/wiredoor/releases)
