# Quick Proxy

```
ssh -R 0.0.0.0:8000:127.0.0.1:3000 root@23.88.63.44
```

`/etc/ssh/sshd_config`
```bash
GatewayPorts clientspecified
```

Install caddy
```bash
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy
```

`/etc/caddy/Caddyfile`
```
https://dominio.com {
    reverse_proxy * http://127.0.0.1:8000
}
```
