import cv2
import time
import os

# === Config ===
capture_interval = 0.2  # seconds (200ms)
num_images = 10
save_dir = "captured_images"

# Create directory if it doesn't exist
os.makedirs(save_dir, exist_ok=True)

# Open the default camera (use 0; try 1 or 2 if you have multiple)
cap = cv2.VideoCapture(2)

if not cap.isOpened():
    print("Error: Could not open the camera.")
    exit()

print("Starting image capture...")

for i in range(num_images):
    ret, frame = cap.read()
    if not ret:
        print(f"Warning: Frame {i} could not be read.")
        continue

    filename = os.path.join(save_dir, f"image_{i:03d}.png")
    cv2.imwrite(filename, frame)
    print(f"Saved {filename}")

    time.sleep(capture_interval)

cap.release()
print("Image capture complete.")
