# RaspberryPi 4 Jupyterlab (Docker)

Minimal Dockerfile to run JupyterLab on an RaspberryPi 4 (arm64). Preinstalled IPython and Ijavascript core  Well suited to include them in IoT services like Balena.

### Docker-Compose example, as it can also be found in the repository:
```yaml
version: '2.1'

services:
  jupyterlab:
    image: silaskalmbach/jupyterlab:latest
    # build: 
    #   context: .
    #   dockerfile: Dockerfile
    restart: unless-stopped
    volumes:
      - jupytercache:/home/workdir
    environment:
      SERVICE_NAME: jupyterlab
      TZ: Europe/Berlin
      TOKEN: secure_token
      PASSWORD: secure_psw
      PORT: 8888
    ports:
      - 80:8888
    
volumes:
  jupytercache:
```

---
© Silas Kalmbach