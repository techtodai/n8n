# Instalación de n8n en docker compose por Tech TodAI
Aquí puedes encontrar los pasos y archivos seguidos en el tutorial de instalación de n8n en docker compose.

Vídeo: https://youtu.be/-eJHqN-Vwt8?si=TfIOX9xnvXahigtB


# 🚀 Instalación de n8n en Ubuntu Server con Docker Compose

En este repositorio encontrarás la guía paso a paso para instalar **[n8n](https://n8n.io/)** en un servidor Ubuntu utilizando **Docker Compose**.

n8n es una herramienta de automatización de flujos de trabajo (workflow automation) de código abierto, ideal para quienes buscan integrar servicios, manejar datos y potenciar proyectos personales o profesionales sin depender de plataformas externas.

---

## 📹 Video tutorial
En este video te enseño cómo instalar n8n en Ubuntu Server utilizando Docker Compose, paso a paso y desde cero.

### [https://youtu.be/-eJHqN-Vwt8?si=TfIOX9xnvXahigtB](https://youtu.be/-eJHqN-Vwt8?si=TfIOX9xnvXahigtB)
---

## 🛠️ Comandos usados en el tutorial

### 1. Conectarse al servidor por SSH
```bash
ssh usuario@IP-del-servidor
```

### 2. Actualizar el sistema
```bash
sudo apt update && sudo apt upgrade -y
```

### 3. Instalar editor de texto (nano)
```bash
sudo apt install nano
```

### 4. Crear carpetas para Docker y n8n
```bash
mkdir docker
cd docker
mkdir n8n
cd n8n
```

### 5. Crear archivo de configuración
```bash
nano [docker-compose.yml](https://github.com/techtodai/n8n/blob/main/docker-compose.yml)
```

Ejemplo de configuración mínima:
```yaml
#Archivo proporcionado por Tech TodAI

services:
  n8n:
    image: n8nio/n8n:latest
    container_name: n8n
    restart: unless-stopped
    ports:
      - "5678:5678"
    environment:
      - N8N_HOST=0.0.0.0
      - N8N_PORT=5678
      - N8N_PROTOCOL=http
      - WEBHOOK_URL=http://192.168.0.20:5678
      - TZ=Europe/Madrid
      - NODE_ENV=production
      - N8N_SECURE_COOKIE=false
      - N8N_RUNNERS_ENABLED=true
    volumes:
      - n8n_data:/home/node/.n8n
      - ./local-files:/files

volumes:
  n8n_data:
```

### 6. Ejecutar el contenedor en segundo plano
```bash
sudo docker compose up -d
```

### 7. Ver contenedores en ejecución
```bash
sudo docker ps
```

### 8. Revisar logs de un contenedor
```bash
sudo docker logs ID-del-contenedor
```

### 9. Acceso desde navegador
```
http://IP-del-servidor:5678
```

---

## 🌍 Zonas horarias válidas
Consulta la lista completa en Wikipedia:  
[Lista de zonas horarias](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List)

---

## 🎯 Lo que aprenderás con este tutorial
- Conexión al servidor por SSH desde PowerShell  
- Actualización básica del sistema Ubuntu  
- Instalación de un editor de texto (nano)  
- Creación de directorios y configuración de `[docker-compose.yml](https://github.com/techtodai/n8n/blob/main/docker-compose.yml)`  
- Ejecución de n8n en contenedor con Docker Compose  
- Acceso al panel de login y activación de funcionalidades premium gratuitas  
- Breve recorrido por la interfaz y creación de un flujo de automatización básico  

---

## ✔️ Beneficios de usar n8n en tu propio servidor
- Más privacidad y control sobre tus datos  
- Independencia de servicios externos  
- Flexibilidad para integrar cientos de apps y APIs  
- Aprendizaje técnico real  

---

## 👥 Ideal para
- Entusiastas del **autohosting**  
- Desarrolladores  
- Creadores de contenido  
- Cualquier persona que quiera empezar en el mundo de la **automatización inteligente**  
