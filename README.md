# k8s-yaml-manifests

k8s-yaml-manifests/
├── README.md
│
├── argo-apps/              # <-- ARGOCD APPLICATION DEFINITIONS
│   │
│   ├── 0-app-of-apps.yaml  # <-- The "root" app you manually apply
│   │
│   ├── dev/                # Argo apps for the 'dev' environment
│   │   ├── service-1-api-app.yaml
│   │   ├── service-2-worker-app.yaml
│   │   └── ...
│   │
│   ├── staging/
│   │   ├── service-1-api-app.yaml
│   │   └── ...
│   │
│   └── prod/
│       ├── service-1-api-app.yaml
│       └── ...
│
├── dev/                    # <-- All 'dev' environment manifests
│   ├── service-1-api/
│   │   ├── deployment.yaml   # <-- CI pipeline edits image tag here
│   │   ├── service.yaml
│   │   └── configmap.yaml
│   │
│   ├── service-2-worker/
│   │   ├── deployment.yaml
│   │   └── configmap.yaml
│   └── ...
│
├── staging/                # <-- All 'staging' environment manifests
│   ├── service-1-api/
│   │   ├── deployment.yaml   # Has staging replicas, configs, & image
│   │   ├── service.yaml
│   │   └── configmap.yaml
│   │
│   ├── service-2-worker/
│   │   └── ...
│   └── ...
│
└── prod/                   # <-- All 'prod' environment manifests
    ├── service-1-api/
    │   ├── deployment.yaml   # Has prod replicas, configs, & image
    │   ├── service.yaml
    │   └── configmap.yaml
    │
    ├── service-2-worker/
    │   └── ...
    └── ...