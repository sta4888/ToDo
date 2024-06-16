# ToDo
personal daily

## Планировщик задач на день


## Requirements:

Установите необходимое ПО:

1. [Docker Desktop](https://www.docker.com).
2. [Git](https://github.com/git-guides/install-git).
3. [PyCharm](https://www.jetbrains.com/ru-ru/pycharm/download) (optional). или [VSCode](https://code.visualstudio.com/download)


## Installation

Склонируйте репозиторий на свой ПК или сервер

1. Для настройки конфигураций, скопируйте файл `.env.sample` в `.env` файл:
    ```shell
    cp .env.sample .env
    ```
   
2. Build the container using Docker Compose:
    ```shell
    docker compose build
    ```
    This command should be run from the root directory where `Dockerfile` is located.
    You also need to build the docker container again in case if you have updated `requirements.txt`.
   
3. Now it is possible to run the project inside the Docker container:
    ```shell
    docker compose up
    ```
   When containers are up server starts at [http://0.0.0.0:8000](http://0.0.0.0:8000). You can open it in your browser.

4. To run application correctly set up the database using commands:
    Connect to the application Docker-container:
    ```shell
    docker compose exec app bash
    ```
   Apply migrations to create tables in the database:
    ```shell
    ./manage.py migrate
    ```

## Usage

1. To manage your new portfolio website you need to add superuser.
    Connect to the application Docker-container (if you are outside the container):
    ```shell
    docker compose exec app bash
    ```
   Create superuser:
    ```shell
    ./manage.py createsuperuser
    ```
2. Go to [http://0.0.0.0:8000/admin](http://0.0.0.0:8000/admin) and manage your jobs and blog posts.

