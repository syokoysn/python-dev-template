FROM python:3.11-slim-bullseye
RUN apt-get update && apt-get install -y \
    git

ENV PYTHONDONTWRITEBYTECODE 1 \
    PYTHONUNBUFFERED 1 \
    POETRY_VERSION=1.4.2

RUN apt-get update && apt-get install -y \
    git \
    curl 

RUN curl -sSL https://install.python-poetry.org | POETRY_HOME=/opt/poetry python3 - && \
    ln -s /opt/poetry/bin/poetry /usr/local/bin/poetry

COPY pyproject.toml poetry.lock ./
RUN poetry config virtualenvs.create false \
    && poetry install