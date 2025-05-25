# Self-Driving Car Simulation Controller

This project connects a trained neural network model with the [Udacity Self-Driving Car Simulator](https://github.com/udacity/self-driving-car-sim) to control a car autonomously based on real-time image data.

## 📦 Project Structure

- `model/model.h5`: Trained Keras model file.
- `drive.py`: Main Python server that receives simulator images, predicts steering angles, and sends control commands back.

---

## 🚀 How to Run This Project

Follow these steps carefully:

### 1. Install Udacity Self-Driving Car Simulator
- Download the simulator:
  - [Udacity Simulator for Windows/Mac/Linux](https://github.com/udacity/self-driving-car-sim/releases)
- Install and open the simulator.
- Select **"Autonomous Mode"** when you start it (after you connect this server).

### 2. Clone this Repository

```bash
git clone https://github.com/sanjaybarla/self_driving_car_udacity.git
cd self_driving_car_udacity
```

### 3. Set Up Python Environment

Make sure you have Python 3.6 or higher.

### 4. Install Required Libraries

```bash
pip install -r requirements.txt
```

### 5. Run the Python Server

```bash
python server.py
```
The server will start listening on port 4567.
You should see
```bash
connected
```

### 6. Start the Simulator

- Open the Udacity Self-Driving Car Simulator.
- Select "Autonomous Mode".
- Click "Select".
- The simulator will now send camera images to your server, and your server will respond with steering and throttle commands!

---

## 🧠 Notes
This project uses a trained deep learning model to predict steering angles based on preprocessed images.
Throttle is adjusted dynamically based on the speed (simple formula: throttle = 1.0 - (speed / speed_limit)).
Image preprocessing includes cropping, color space conversion (RGB → YUV), Gaussian blur, resizing, and normalization.

---

## 📷 Image Preprocessing
- Incoming camera images are processed with:
- Crop (remove sky and car hood)
- Convert RGB to YUV color space
- Apply Gaussian blur
- Resize to (200x66) pixels
- Normalize pixel values between 0 and 1


This matches the Nvidia end-to-end self-driving car model training approach.

--- 

# 🎉 That's it! Happy Driving!
