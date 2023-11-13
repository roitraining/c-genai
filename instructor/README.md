# Vertex Search

## Setup

1. Configure the Google Cloud SDK to point to the classroom project
2. Clone this repo
3. Deploy the index to an endpoint (sub values for placeholders)

   ```bash
   cd c-genai/instructor
   export PROJECT_ID="class-project-id"
   export INITIALS="your-initials"
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.xt
   python v-setup.py
   ```

   This process will take 20-30 minutes to finish

4. Copy the `endpoint_id` and `deployed_index_id` to a file so you can share 
   with students later
5. Modify the **add-a-role** Cloud Run service to allow external requests
   ```bash
   sh net.sh
   ```

## Cleanup

1. Undeploy the model and remove the endpoint (replace placeholder)
   ```bash
   PROJECT_ID="class-project-id"
   python v-clean.py
   ```

2. Modify the **add-a-role** Cloud Run service to allow only internal requests
   ```bash
   sh net.sh
   ```