# Dockerfile References: https://docs.docker.com/engine/reference/builder/

# Start from the latest golang base image
FROM golang:latest

# Set the Current Working Directory inside the container
WORKDIR /app

# Add files to app folder
ADD . /app

# Build the Go app
RUN go build -o main .

# Expose ports to the outside world
EXPOSE 3500

COPY datadog-init /app/datadog-init
ENTRYPOINT ["/app/datadog-init"]

ENV DD_SERVICE=album-api
ENV DD_ENV=dev
ENV DD_VERSION=11
ENV DD_API_KEY=
ENV DD_TRACE_ENABLED=true
ENV DD_AZURE_SUBSCRIPTION_ID=e4b8045f-4ee4-47a6-818f-1fe88b3016a7
ENV DD_AZURE_RESOURCE_GROUP=album-containerapps
ENV DD_SITE=datad0g.com

# Command to run the executable
CMD ["./main"]
