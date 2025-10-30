# 📊 Motion Chart – Helm Chart Guide
# 🧭 Overview

This Helm Chart is used to deploy and manage the Motion Chart application on your Kubernetes cluster.
Follow the steps below to package, update, and publish the chart to your Helm repository.

🚀 How to Use Motion Chart
1. Package the Helm Chart

Run the following command to create a packaged .tgz file from your chart directory:

`helm package motion-chart`


This will generate a file like:

`motion-chart-<version>.tgz`

2. Update the Helm Repository Index

After packaging, update the Helm repository index so Helm can recognize the new chart version:

`helm repo index .`


This command will update (or create) the index.yaml file in your Helm chart repository directory.

3. Push to Git Repository

Commit and push the changes (including .tgz and index.yaml) to your Git repository:

`git add .`
`git commit -m "chore: update motion-chart helm package"`
`git push origin main`


Make sure the repository (for example, GitHub Pages or GitHub Enterprise) is correctly configured as a Helm Chart repository.

# ⚙️ Example: Add Helm Repo and Install

You can add the repository and install the chart as follows:

`helm repo add motion-chart-repo https://yazidalg.github.io/motion-chart/`
`helm repo update`
`helm install my-motion motion-chart-repo/motion-chart`

# 🧩 Notes

Ensure your repository is accessible publicly or authenticated properly if using GitHub Enterprise.

Each chart update requires re-running:

`helm package motion-chart`

`helm repo index .`

Git push
