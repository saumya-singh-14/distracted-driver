# Eyes on the Road: Real-Time Driver State Analysis

A real-time driver monitoring system that uses computer vision techniques to detect drowsiness, gaze deviation, and head pose distraction using only a webcam. Built with Python, OpenCV, and MediaPipe, this system tracks eye closure, gaze direction, and head orientation to assess the driver's alertness level.

# Features

Real-time face landmark detection using MediaPipe Face Mesh (478 landmarks)

Drowsiness detection via Eye Aspect Ratio (EAR)

Gaze deviation detection using iris distance from eye center

Head pose estimation (yaw, pitch, roll) using solvePnP

Calculates PERCLOS — Percentage of Eye Closure — to monitor fatigue

Displays live stats: EAR, Gaze Score, PERCLOS, FPS, and warning overlays

# How It Works

Capture Frame: Reads real-time video stream from the webcam.

Detect Landmarks: Uses MediaPipe to extract 3D face landmarks.

Compute Metrics:

  EAR to detect prolonged eye closure
  
  Gaze Score to detect if the driver is looking away
  
  Head Pose to detect distraction

Score Attention: Flags states like-

  ASLEEP, LOOKING AWAY, DISTRACTED, TIRED

Display Warnings on the video feed in real time.

# Tech Stack

Language: Python

Libraries: OpenCV, MediaPipe, NumPy

Core Concepts: EAR, Gaze Tracking, Head Pose Estimation, PERCLOS

# Thresholds Used

EAR	< 0.15 (Eye closure detection)

EAR Time	> 4 sec	(Drowsiness)

Gaze Score	> 0.015	(Gaze deviation)

PERCLOS	> 0.2	(Fatigue over 60 seconds)

Yaw / Pitch / Roll	> 20–30°	(Head movement distraction)

# Installation

git clone https://github.com/yourusername/driver-state-analysis.git  
cd driver-state-analysis  
pip install -r requirements.txt
python main.py  

# Requirements

A working webcam

Python 3.7+

Recommended: Run on CPU (no GPU required)

