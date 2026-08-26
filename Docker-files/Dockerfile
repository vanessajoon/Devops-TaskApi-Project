FROM python:3.12-slim

WORKDIR /app

# copy and install dependencies first to leverage docker caching layers
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# copying the rest of the application
COPY app/ ./app/

# Tell flask where you app file is located
ENV FLASK_APP=app/app.py

EXPOSE 5000

# Run Flask listening on all network interfaces (0.0.0.0)
CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]