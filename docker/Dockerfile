FROM python:3.11-slim

LABEL maintainer="Passwork Team"
LABEL description="Passwork CLI Docker Image for CI/CD pipelines"

# Set working directory
WORKDIR /app

# Copy source code
COPY . .

# Install passwork-cli
RUN pip install --no-cache-dir .

# Create a non-root user to run the CLI
RUN groupadd -r passwork --gid=1001 && \
  useradd -r -g passwork --uid=1001 passwork

USER passwork

# Set the entrypoint to passwork-cli
ENTRYPOINT ["passwork-cli"]
CMD ["--help"]
