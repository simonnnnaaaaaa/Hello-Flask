# Hello Flask in Docker & Kubernetes 🚀

This project is a simple **Python Flask** application, containerized with Docker and deployed on a local Kubernetes cluster (using Rancher Desktop).

---

## 📦 Prerequisites
- [Rancher Desktop](https://rancherdesktop.io/) installed
- `nerdctl` (comes with Rancher Desktop)
- `kubectl` (comes with Rancher Desktop)
- Git (for version control)

---

## 🐳 Docker

1. **Build the image:**
   ```bash
   nerdctl build -t hello-flask:1.0 .
Run the container:

bash
Copy code
nerdctl run --rm -p 8080:8080 --name hello-flask hello-flask:1.0
Open in your browser:

arduino
Copy code
http://localhost:8080
☸️ Kubernetes
Build the image inside the Kubernetes namespace:

bash
Copy code
nerdctl --namespace k8s.io build -t hello-flask:1.0 .
Apply the manifests:

bash
Copy code
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
Check resources:

bash
Copy code
kubectl get pods
kubectl get svc
Port-forward the service:

bash
Copy code
kubectl port-forward service/hello-flask-service 8080:8080
Open in your browser:

arduino
Copy code
http://localhost:8080
🧹 Cleanup
When you’re done testing, delete the resources from the cluster:

bash
Copy code
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml
📂 Project structure
Copy code
hello-flask/
├── app.py
├── requirements.txt
├── Dockerfile
├── deployment.yaml
├── service.yaml
└── README.md
🙌 Result
The application displays:

Copy code
Hello, World! 👋
both when running in Docker and when deployed on Kubernetes.

yaml
Copy code

---

✨ If you also want to make your GitHub repo look more professional, you can add **screenshots** (like your terminal build output or the browser result). For example, in the README:

```markdown
## Screenshots

### Running in Docker
![Docker run](images/docker-run.png)

### Accessing in Browser
![Hello World](images/hello-world.png)
