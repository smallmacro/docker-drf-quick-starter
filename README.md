# docker-drf-quick-starter
This starter employs Django, Django Rest Framework, and PostgreSQL to construct a REST API with OpenAPI documentation, integrated with Docker, Docker Compose, and GitHub Actions.
## Features

- Django web application framework
- Postgresql database
- Redis in-memory data structure store
- Github Actions. For automatic testing , linting and Deployment. In order to connect the github with docker hub, we need to add Docker Hub's `account name` and `access token` into github repository secrets.
- Test Driven Development. Write Test -> Run Test(fail) -> add Feature -> Run Test(Passes)
- Docker. Utilize the Docker hub authenticated access 200 pull/6h
- Test Driven Development. base on `unittest` library and Django REST Framework test features. 
- Fix database race condition by customing Django management command `wait_for_db`. [Django Docs management command](https://docs.djangoproject.com/en/5.0/topics/testing/tools/#topics-testing-management-commands)

## Included Packages and Tools
- `Docker` and Docker Hub account for pulling images for Python and Postgresql. [Anonymous users vs authorized users rate limits](https://docs.docker.com/docker-hub/download-rate-limit/)
- `Github Actions` for automatic linting and testing.(Need to set up docker hub token in github secrets in order to pull images from Dock hub)
- `Django` and `Django REST Framework`
- `Postgresql`
- `Psycopg2`, the postgresql database adaptor for python, requirs additional dependencies: `build-base`, `postgresql-dev`, `musl-dev`, `postgresql-client`
- `flake8` for linting. 
- `Pillow` for image uploading
- `drf-spectacular`for OPENAPI docs

## Linting and Testing Commands
```shell
# app is the name of service.
docker-compose run --rm app sh -c "flake8"   #linting
docker-compose run --rm app sh -c "python manage.py test"   #tesing
```

## Requirements
- Django>=4.0.1,<4.1
- djangorestframework>=3.13.1,<3.14
- psycopg2>=2.9.3,<2.10
- drf-spectacular>=0.22.1,<0.23
- Pillow>=9.1.0,<9.2
- uwsgi>=2.0.20,<2.1
- flake8>=4.0.1,<4.1

## Django Project structure

