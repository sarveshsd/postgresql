# Integrating PostgreSQL Exporter with PostgreSQL Database on Kubernetes

This guide will walk you through the process of integrating the PostgreSQL exporter with your PostgreSQL database running on Kubernetes. The PostgreSQL exporter collects and exposes metrics from PostgreSQL databases, allowing you to monitor database performance and health using Prometheus.

## Prerequisites

Before you begin, ensure that you have the following:

- A Kubernetes cluster up and running.
- `kubectl` command-line tool installed and configured to connect to your Kubernetes cluster.
- Helm installed (optional, if you're using Helm charts).

## Steps

### 1. Deploy PostgreSQL Exporter

Deploy the PostgreSQL exporter alongside your PostgreSQL database on Kubernetes. You can use a Helm chart or manually create Kubernetes manifests for the exporter deployment and service. Ensure that the exporter is configured to connect to your PostgreSQL database.

      cd prometheus-postgres-exporter
      helm install postgres .

### 2. Configure Prometheus

Add a scrape configuration for the PostgreSQL exporter in your Prometheus configuration file (`prometheus.yml`). This configuration should specify the target endpoint of the exporter and any necessary job-specific configurations.

    kubectl apply -f prometheus-deployment.yaml
    kubectl apply -f prom-conf.yaml

### 3. Configure Grafana

    kubectl apply -f grafana.yaml

### 4. Verify Configuration

After deploying both the PostgreSQL exporter and Prometheus, verify that Prometheus is successfully scraping metrics from the exporter. You can check Prometheus's targets page to see if the exporter is listed and whether it is successfully scraping metrics.


### 5. POC

    https://drive.google.com/file/d/16BqLF6UPPNrMwP9I3981u0ftYvYmRpCM/view?usp=sharing
