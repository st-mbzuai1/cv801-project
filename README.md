# vid2vid — README


---

## 1) Download code & environment files

All required files are provided in this Google Drive folder:

- **Drive link:**  
  https://drive.google.com/drive/folders/115fnzYzNVqbq0CTUqqaSSDwe5T_qI9a-?usp=sharing

> **What’s inside:** the code snapshot and an environment spec file (e.g., `environment.yml` or `requirements.txt`). Download the folder locally.

---

## 2) Build the environment

> You only need **one** of the following, depending on which file is provided in the Drive folder.

### Option A — Using Conda (if `environment.yml` is provided)
```bash
# create env from YAML
conda env create -f environment.yml
conda activate streamv2v_working

```

**System notes (typical):**
- NVIDIA GPU + recent CUDA drivers recommended for realtime/fast inference.
- FFmpeg often required for reading/writing videos (`ffmpeg` in PATH).

---


## 3) How to run

### A) Run the full evaluation (all source videos & prompts)
From the project’s `vid2vid` folder:
```bash
cd streamv2v/vid2vid
bash run_prompts_corrected.sh
```

This script will iterate through the evaluation source videos and prompts and write outputs to the configured directory.

### B) Run a single video with a custom prompt
From the same folder:
```bash
python main.py   --input_path ./demo_selfie/jeff_1.mp4   --prompt "Elon Mush is giving a talk"   --output_path ./outputs/elon_talking_2.mp4
```

**Arguments**
- `--input_path` : path to the source video file
- `--prompt`     : your text prompt
- `--output_path`: where to save the generated video

---

