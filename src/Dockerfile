FROM debian:trixie-backports

RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y --no-install-recommends python3 python3-pip \
    && rm -rf /var/lib/apt/lists/*

RUN useradd --create-home user49

WORKDIR /app

COPY requirements.txt .

RUN pip3 install --no-cache-dir --break-system-packages -r requirements.txt

COPY server.py .

USER user49

EXPOSE 5000

CMD [ "python3", "server.py" ]
