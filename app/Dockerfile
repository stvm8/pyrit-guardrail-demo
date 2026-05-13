FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY main.py .

# Default: strong guardrail. Override with -e GUARDRAIL_STRENGTH=weak to demo failures.
ENV GUARDRAIL_STRENGTH=strong
ENV APP_AUTH_TOKEN=demo-secret-token-123

EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
