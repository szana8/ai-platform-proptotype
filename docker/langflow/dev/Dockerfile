FROM langflowai/langflow:${LANGFLOW_VERSION}

RUN mkdir /app/flows
RUN mkdir /app/langflow-config-dir
WORKDIR /app

# Research how to use custom components in Langflow
# COPY ./custom_flows /app/flows
# COPY ./langflow-components /app/custom_components

COPY .env /app/.env

ENV PYTHONPATH=/app
ENV LANGFLOW_LOAD_FLOWS_PATH=/app/flows
ENV LANGFLOW_LOG_ENV=container

# ENV LANGFLOW_CONFIG_DIR=/app/langflow-config-dir
#ENV LANGFLOW_COMPONENTS_PATH=/app/custom_components

# Install dependencies
# RUN uv pip install langflow helpful-review-predictor

EXPOSE 7860
CMD ["langflow", "run", "--env-file","/app/.env","--host", "0.0.0.0", "--port", "7860"]
