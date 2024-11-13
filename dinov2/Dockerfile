# Use NVIDIA's Python-CUDA image as a base
FROM nvcr.io/nvidia/ai-workbench/python-cuda117:1.0.3

# Set a working directory in the container
WORKDIR /app

# Copy the requirements files into the container
COPY requirements.txt requirements-dev.txt requirements-extras.txt dinov2 ./

RUN pip install --no-cache-dir -r requirements.txt \
    && pip install --no-cache-dir -r requirements-dev.txt \
    && pip install --no-cache-dir -r requirements-extras.txt

# RUN git clone https://github.com/facebookresearch/dinov2.git

# Copy the rest of the application code into the container
COPY . .

# Expose port 1425 to allow external access
EXPOSE 1425

# Specify the default command to run your application
CMD ["python3", "app.py"]

# Example to build the image: docker build -t surajmurari/image-name:latest .
