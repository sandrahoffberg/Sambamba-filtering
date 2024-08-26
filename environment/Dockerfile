# hash:sha256:6667bd1ef48b38064b9f11ed4a828291b89e9de31616b01f5209a9927cccf6cc
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:22.11.1-4-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN mamba install -y --channel=bioconda \
        ca-certificates==2023.7.22 \
        git==2.42.0 \
        sambamba==1.0 \
    && mamba clean -ya

RUN pip install -U --no-cache-dir \
    code-ocean-aux-tools==1.1.3

COPY postInstall /
RUN /postInstall
