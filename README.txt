# Static share folder

Open locally:
  cd static_share && python3 -m http.server 8080
  → http://localhost:8080

Share as ZIP:
  cd .. && zip -r invar-static-share.zip static_share/
  Email or Drive the zip — recipient unzips and opens index.html

Host on Google Cloud Storage (static website):
  gsutil mb -l asia-south1 gs://YOUR-BUCKET-NAME
  gsutil -m cp -r static_share/* gs://YOUR-BUCKET-NAME/
  gsutil web set -m index.html -e index.html gs://YOUR-BUCKET-NAME
  gsutil iam ch allUsers:objectViewer gs://YOUR-BUCKET-NAME
  → https://storage.googleapis.com/YOUR-BUCKET-NAME/index.html

For the full interactive app (charts + live trace), use Cloud Run instead — DEPLOY_GCP.md
