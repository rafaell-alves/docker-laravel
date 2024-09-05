# Laravel utilizando Docker

Este é um projeto Laravel configurado para rodar em um ambiente Docker com suporte a MySQL, Redis, RabbitMQ e Grafana.

## Pré-requisitos

Antes de começar, você vai precisar ter instalado em sua máquina:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Passos para rodar o projeto

### 1. Modifique o .env para sua escolhas

Antes de rodar o projeto, configure as variáveis de ambiente no arquivo .env. Você pode usar o .env-example como base. Aqui estão as variáveis de ambiente principais:

`APP_NAME`

`APP_ENV`

`APP_KEY`

`APP_DEBUG`

`APP_URL`

`APP_PORT`

`LOG_CHANNEL`

`LOG_DEPRECATIONS_CHANNEL`

`LOG_LEVEL`

`DB_CONNECTION`

`DB_HOST`

`DB_PORT`

`DB_DATABASE`

`DB_USERNAME`

`DB_PASSWORD`

`BROADCAST_DRIVER`

`CACHE_DRIVER`

`FILESYSTEM_DISK`

`QUEUE_CONNECTION`

`SESSION_DRIVER`

`SESSION_LIFETIME`

`MEMCACHED_HOST`

`REDIS_HOST`

`REDIS_PASSWORD`

`REDIS_PORT`

`MAIL_MAILER`

`MAIL_HOST`

`MAIL_PORT`

`MAIL_USERNAME`

`MAIL_PASSWORD`

`MAIL_ENCRYPTION`

`MAIL_FROM_ADDRESS`

`MAIL_FROM_NAME`

`AWS_ACCESS_KEY_ID`

`AWS_SECRET_ACCESS_KEY`

`AWS_DEFAULT_REGION`

`AWS_BUCKET`

`AWS_USE_PATH_STYLE_ENDPOINT`

`PUSHER_APP_ID`

`PUSHER_APP_KEY`

`PUSHER_APP_SECRET`

`PUSHER_HOST`

`PUSHER_PORT`

`PUSHER_SCHEME`

`PUSHER_APP_CLUSTER`

`VITE_APP_NAME`

`VITE_PUSHER_APP_KEY`

`VITE_PUSHER_HOST`

`VITE_PUSHER_PORT`

`VITE_PUSHER_SCHEME`

`VITE_PUSHER_APP_CLUSTER`

`RABBIT_MQ_PORT`

`RABBIT_MQ_EXTERNAL_PORT`

`RABBIT_MQ_USER`

`RABBIT_MQ_PASSWORD`

### 2. Rode o comando docker

Para construir e rodar os containers do Docker, utilize o seguinte comando:

```bash 
docker-compose up --build
```

### 3. Instalação dos pacotes e migrate

Após iniciar os containers, execute os comandos a seguir dentro do container PHP para instalar os pacotes e rodar as migrations e seeds:

```bash 
docker exec {nome_do_container}-php compose install
docker exec {nome_do_container}-php php artisan migrate
docker exec {nome_do_container}-php php artisan db:seed
```
