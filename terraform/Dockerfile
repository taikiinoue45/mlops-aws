FROM ubuntu:18.04

RUN set -xe \
        && apt-get update \
        && apt-get install -y --no-install-recommends ca-certificates git unzip wget \
        #
        # Install aws-cli
        && wget https://awscli.amazonaws.com/awscli-exe-linux-x86_64-2.2.27.zip \
        && unzip awscli-exe-linux-x86_64-2.2.27.zip \
        && ./aws/install \
        && rm -rf aws awscli-exe-linux-x86_64-2.2.27.zip \
        #
        # Install terraform
        && wget https://releases.hashicorp.com/terraform/1.1.7/terraform_1.1.7_linux_amd64.zip \
        && unzip terraform_1.1.7_linux_amd64.zip \
        && mv terraform /usr/local/bin/ \
        && rm terraform_1.1.7_linux_amd64.zip \
        #
        # Cleanup
        && apt-get autoremove -y \
        && apt-get autoclean -y \
        && rm -rf /var/lib/apt/lists/*
