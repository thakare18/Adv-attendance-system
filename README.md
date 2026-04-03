# Face Recognition Based Attendance Monitoring System

A desktop application that automates classroom attendance using computer vision and face recognition.

This project demonstrates an end-to-end ML-powered workflow: student registration, face dataset collection, model training, and real-time attendance logging through a user-friendly Tkinter interface.

## Project Highlights

- Real-time face detection using OpenCV Haar Cascade.
- Face recognition with LBPH (Local Binary Pattern Histogram).
- Automated attendance generation in date-wise CSV files.
- GUI-driven experience for non-technical users (registration, training, and tracking).
- Password-protected model training workflow.
- Lightweight local-first architecture with no cloud dependency.

## Why This Project Matters

Manual attendance is time-consuming and error-prone. This system improves operational efficiency by reducing manual effort, minimizing proxy attendance risks, and providing structured digital records that can be reviewed and audited.

## Tech Stack

- Python
- OpenCV (`opencv-contrib-python`)
- NumPy
- Pandas
- Pillow
- Tkinter (standard Python GUI library)

## Core Workflow

1. Register a student by entering `ID` and `Name`.
2. Capture face samples (`~100` images) via webcam.
3. Train the LBPH recognizer and save model weights.
4. Start attendance mode to identify faces in real time.
5. Export attendance entries to date-wise CSV files in the `Attendance/` directory.

## Repository Structure

```text
.
|-- main.py
|-- requirements.txt
|-- haarcascade_frontalface_default.xml
|-- install commands .txt
|-- Attendance/
|-- StudentDetails/
|-- TrainingImage/
`-- TrainingImageLabel/
```

## Getting Started

### 1) Clone the Repository

```bash
git clone <your-repository-url>
cd "Face Recognition Based Attendance Monitoring System"
```

### 2) Create and Activate Virtual Environment

Windows (PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3) Install Dependencies

```bash
python -m pip install -r requirements.txt
```

If needed, install directly:

```bash
python -m pip install opencv-contrib-python numpy pillow pandas
```

### 4) Run the Application

```bash
python main.py
```

## How To Use

### A. New Registration

1. Enter Student ID.
2. Enter Student Name.
3. Click **Take Images** to capture training samples.
4. Click **Save Profile** to train and save the recognizer model.

### B. Mark Attendance

1. Click **Take Attendance**.
2. Stand in front of the webcam.
3. Press `q` to stop capture.
4. Check generated CSV in `Attendance/Attendance_DD-MM-YYYY.csv`.

## Output Artifacts

- Student metadata: `StudentDetails/StudentDetails.csv`
- Captured face dataset: `TrainingImage/`
- Trained model: `TrainingImageLabel/Trainner.yml`
- Daily attendance logs: `Attendance/Attendance_DD-MM-YYYY.csv`

## Security Note

The training action is protected with a local password stored in `TrainingImageLabel/psd.txt`. For production-grade usage, this should be replaced with a secure hashed credential mechanism.

## Known Limitations

- Recognition quality depends on lighting, camera angle, and face visibility.
- Single-camera local setup only (no centralized multi-device sync).
- Password storage is plain text in the current implementation.

## Future Enhancements

- Liveness detection to prevent spoofing.
- Strong authentication and encrypted credential storage.
- Database-backed attendance analytics dashboard.
- Multi-class/course support with role-based access.
- Cloud sync and API integration for ERP/LMS systems.

## Contact

Prathamesh Thakare
Contact: prathamthackeray@gmail.com
