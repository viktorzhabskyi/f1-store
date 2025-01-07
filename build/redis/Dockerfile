FROM python:3.12

RUN apt-get update && apt-get install -y \
    python3-distutils \
    python3-apt \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip setuptools wheel

WORKDIR /code

COPY ./backend_redis/ /code/

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

ENTRYPOINT ["python", "manage.py", "runserver", "0.0.0.0:8000"]