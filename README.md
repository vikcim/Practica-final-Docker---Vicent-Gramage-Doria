# Práctica Final Docker - Vicent Gramage Doria

Esta práctica utiliza Docker y Docker Compose para desplegar una aplicación compuesta por varios servicios. La aplicación incluye una base de datos MongoDB, una interfaz web para administrar MongoDB (Mongo Express), un backend, un frontend, un balanceador de carga Nginx, un servidor de métricas Prometheus y un tablero de visualización Grafana.

## Servicios

- **MongoDB (mongo_container)**:
  - Puerto: No expuesto al exterior
  - Imagen: mongo
  - Reinicio: Siempre

- **Mongo Express (adminMongo_container)**:
  - Puerto: 8081
  - Imagen: mongo-express
  - Reinicio: Siempre

- **Backend (backend_container)**:
  - Puerto: No expuesto al exterior
  - Imagen: Personalizada (definida en Dockerfile)

- **Frontend (frontend_container)**:
  - Puerto: No expuesto al exterior
  - Imagen: Personalizada (definida en Dockerfile)

- **Nginx (nginx_container)**:
  - Puerto: 80
  - Imagen: nginx
  - Reinicio: Siempre

- **Prometheus (prometheus_container)**:
  - Puerto: 9090
  - Imagen: prom/prometheus:v2.20.1
  - Reinicio: Siempre

- **Grafana (grafana_container)**:
  - Puerto: 3500
  - Imagen: grafana/grafana:7.1.5
  - Reinicio: Siempre

## Archivos

- **Dockerfile**:
  - Se encuentra en la carpeta `./backend` y `./frontend` para construir las imágenes personalizadas.

- **docker-compose.yml**:
  - Define la configuración de todos los servicios y sus dependencias.

- **prometheus.yml**:
  - Contiene la configuración de Prometheus para la recopilación de métricas.

- **nginx.conf**:
  - Configuración del servidor Nginx.

## Ejecución

1. Clonar este repositorio.
2. Asegurarse de tener Docker y Docker Compose instalados.
3. Ejecutar `docker-compose up -d` en el directorio raíz del repositorio.
4. Acceder a la aplicación a través de los puertos especificados en cada servicio.

