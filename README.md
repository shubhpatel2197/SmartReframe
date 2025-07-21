# SmartReframe

Crop any **landscape** video to a **vertical 9 : 16** aspect ratio while automatically keeping the main subject in frame.  
The script relies on **YOLO v8** for object detection and a simple scoring + smoothing routine to decide where to place the crop window.

---

## 📑 What’s inside?

| Component | Role |
|-----------|------|
| `setup_yolo()`            | Loads the pretrained **yolov8l.pt** weights |
| `ObjectScorer`            | Scores detections by distance to centre + size |
| `SubjectTracker`          | Remembers the best-scoring object across frames |
| `calculate_crop_window()` | Computes the 9 : 16 crop (left, top, width, height) |
| `SmoothingBuffer`         | Exponential smoothing so the crop window moves gently |
| `process_video()`         | Reads frames, crops them, writes the output video |

Everything lives in **`main.ipynb`** (export to `.py` if you prefer).

---

## 🛠️ Setup

```bash
# clone the repo / copy the notebook
pip install -r requirements.txt   # or use the one-liner below
# one-liner used in the notebook:
# pip install opencv-python torchvision ultralytics moviepy pyDeepInsight
