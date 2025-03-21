# Use the official Zeek image from Docker Hub
FROM zeek/zeek:latest

# Update package list and install dependencies
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    g++ \
    cmake \
    make \
    libpcap-dev && \
    rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /opt/zeek

# Set the Zeek log directory
ENV ZEEK_LOG_DIR=/logs

# Copy any necessary configuration files
# COPY local.zeek /opt/zeek/share/zeek/site/local.zeek

# Expose necessary ports
EXPOSE 47760

# Start Zeek
CMD ["zeek", "-i", "eth0"]
