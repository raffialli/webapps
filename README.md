
# Flask File Upload App

This is a Flask application that allows users to upload files. It includes user authentication with Flask-Login and handles various file types with a maximum size limit.

## Features

- User authentication using Flask-Login
- File upload functionality with validation for allowed file types
- Display list of uploaded files
- Secure file handling and storage

## Prerequisites

- Python 3.9
- Docker
- Kubernetes (optional for deployment)

## Setup

1. **Clone the repository:**
   ```sh
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Create a virtual environment and install dependencies:**
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scriptsctivate
   pip install -r requirements.txt
   ```

3. **Create a `.env` file:**
   ```plaintext
   FLASK_APP=app.py
   FLASK_ENV=development
   SECRET_KEY=your_secret_key
   USERNAME=your_username
   PASSWORD_HASH=your_password_hash
   ```

4. **Run the application:**
   ```sh
   flask run
   ```

## Docker

1. **Build the Docker image:**
   ```sh
   docker build -t my-flask-app .
   ```

2. **Run the Docker container:**
   ```sh
   docker run --env-file .env -p 5000:5000 my-flask-app
   ```

## Kubernetes

1. **Create Kubernetes secrets:**
   ```sh
   kubectl create secret generic flask-secrets --from-env-file=.env
   ```

2. **Apply deployment and service:**
   ```sh
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```

3. **Access the application:**
   ```sh
   kubectl get services
   # Note the external IP and port, then access it in your browser
   ```

## File Upload

- Allowed file types: `txt`, `pdf`, `png`, `jpg`, `jpeg`, `gif`
- Maximum file size: 16 MB

## Routes

- `/login`: User login
- `/logout`: User logout
- `/`: File upload page (requires login)
- `/uploads/<filename>`: Access uploaded files (requires login)
- `/files`: List of uploaded files (requires login)

## License

This project is licensed under the MIT License. See the LICENSE file for details.
