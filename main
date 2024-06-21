import os
import subprocess
import http.server
import socketserver

# Define the repository URL and the local directory
repo_url = 'https://github.com/senniappasarvesh/Plantify-.git'
local_dir = 'local-repo'

# Step 1: Clone the repository
subprocess.run(['git', 'clone', repo_url, local_dir])

# Step 2: Navigate to the project directory
os.chdir(local_dir)

# Optional: Install dependencies if a package manager like npm is used
# Uncomment the following lines if package.json exists and npm is needed
# if os.path.exists('package.json'):
#     subprocess.run(['npm', 'install'])

# Step 3: Serve the files using Python's built-in HTTP server
PORT = 8000
Handler = http.server.SimpleHTTPRequestHandler

with socketserver.TCPServer(("", PORT), Handler) as httpd:
    print(f"Serving at port {PORT}")
    httpd.serve_forever()
