Implementation Guide
Set up AWS credentials:

bash
--aws configure
--terraform init
--terraform apply
-Configure kubectl:

bash
--aws eks --region us-east-1 update-kubeconfig --name app-cluster

Deploy applications:

Bash

kubectl apply -f k8s/
Access the application:

bash

--kubectl get svc frontend-service
# Use the EXTERNAL-IP to access the React app

Repository Structure:

├── .github/
│   └── workflows/
│       ├── frontend-ci-cd.yaml
│       └── backend-ci-cd.yaml
├── backend/
│   ├── Dockerfile
│   └── ...
├── frontend/
│   ├── Dockerfile
│   └── ...
├── k8s/
│   ├── frontend-deployment.yaml
│   ├── backend-deployment.yaml
│   ├── services.yaml
│   ├── monitoring/
│   └── logging/
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
└── README.md