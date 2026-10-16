# hub.wav 🔊 — Sound Design Panel for Adobe Premiere Pro & After Effects

A glassmorphic sound design extension (CEP) built for **Adobe Premiere Pro** and **Adobe After Effects**. It streamlines video editing and motion graphics workflows by allowing editors to audition, organize, and insert sound effects directly onto their active timelines without ever leaving their editing workspace.

---

<img width="816" height="608" alt="With Menu" src="https://github.com/user-attachments/assets/f6616c1a-3051-4576-989e-34c8894f7fde" />

<img width="816" height="611" alt="without menu" src="https://github.com/user-attachments/assets/6155516b-afc6-4596-ab8a-492137b73946" />


## ✨ Features
- **⚡ Instant Playhead Insertion:** Double-click any sound card or hit **"Add to Timeline"** to immediately insert the audio clip at your Current Time Indicator (CTI / Playhead) on an available audio track.
- **📁 Dynamic Category Mapping:** Recursively scans your local sound libraries and automatically maps folder structures (e.g. `Whooshes`, `Impacts`, `Drones`, `Risers`, `Foley`) into interactive category tabs.
- **🎯 Dynamic Host Detection:** Automatically recognizes whether it is running inside **Premiere Pro** or **After Effects** and routes sequence/composition automation scripts accordingly.
- **🌊 Real-Time Waveform Visualizer:** Hardware-inspired audio waveform canvas powered by the Web Audio API with duration readouts and volume sliders.
- **⭐ Safe & Persistent Settings:** Star your favorite sound effects and configure preferences with storage inside your system's personal Documents folder (`Documents/hub.wav/settings.json`). Settings, folders, and favorites remain **100% untouched** across media cache purges, re-installs, and Adobe application updates.
- **🌍 Universal Language Support:** Fully language-independent across macOS and Windows. Automatically resolves the correct Documents folder regardless of OS locale (e.g., German `Dokumente`, English `Documents`, French, Spanish) or Windows OneDrive folder redirections.
- **🎨 Glassmorphic Themes:** Choose between 5 customizable accent themes (`Violet`, `Cyberpunk`, `Matrix`, `Ruby`, `Gold`).
---
## 💻 Supported Applications
- **Adobe Premiere Pro** (v13.0 / CC 2019 and newer, including Premiere Pro 2022–2026+)
- **Adobe After Effects** (v13.0 / CC 2019 and newer, including After Effects 2021–2026+)
---
## 🚀 Installation Guide
Because `hub.wav` is an open-source development extension (CEP), you first enable Adobe's developer debug mode, and then copy the folder into Adobe's extensions directory.
### Step 1: Enable Adobe PlayerDebugMode
Adobe host applications require `PlayerDebugMode` enabled to load unsigned extension panels:
#### **On macOS:**
1. Open the **Terminal** app (`/Applications/Utilities/Terminal.app`).
2. Copy and paste the following commands and hit **Enter**:
```bash
defaults write com.adobe.CSXS.9 PlayerDebugMode 1
defaults write com.adobe.CSXS.10 PlayerDebugMode 1
defaults write com.adobe.CSXS.11 PlayerDebugMode 1
defaults write com.adobe.CSXS.12 PlayerDebugMode 1
defaults write com.adobe.CSXS.13 PlayerDebugMode 1
defaults write com.adobe.CSXS.14 PlayerDebugMode 1
```
#### **On Windows:**
1. Press `Win + X` and open **PowerShell** (or Command Prompt as Administrator).
2. Run the following command:
```powershell
8..14 | ForEach-Object { reg add "HKCU\Software\Adobe\CSXS.$_" /v PlayerDebugMode /t REG_SZ /d 1 /f }
```
*(Alternatively, you can run `npm run setup-debug` or execute `scripts/setup_debug_mode.bat` as Administrator).*
---
### Step 2: Copy the Extension Folder
Move or copy the `hub.wav` folder into Adobe's default user extensions directory:
#### **On macOS:**
Copy the folder to:
```text
~/Library/Application Support/Adobe/CEP/extensions/hub.wav
```
> **Quick Navigation:** In Finder, press `Cmd + Shift + G`, paste `~/Library/Application Support/Adobe/CEP/extensions/` and hit Enter. If the `CEP` or `extensions` folder does not exist, create it manually.
#### **On Windows:**
Copy the folder to:
```text
%APPDATA%\Adobe\CEP\extensions\hub.wav
```
*(Full path: `C:\Users\<Your-Username>\AppData\Roaming\Adobe\CEP\extensions\hub.wav`)*
> **Quick Navigation:** Press `Win + R`, paste `%APPDATA%\Adobe\CEP\extensions` and hit Enter. If the `CEP` or `extensions` folder does not exist, create it manually.
---
### Step 3: Launch in Premiere Pro or After Effects
1. Start (or restart) **Premiere Pro** or **After Effects**.
2. Open a project with an **active sequence** (Premiere) or **composition** (After Effects).
3. In the top application menu bar, go to:
   ```text
   Window > Extensions > hub.wav
   ```
4. The panel will open. Click the **Custom Folders** tab on the left sidebar to add your local SFX libraries.
---
## 🎧 How to Use
1. **Connect Your Libraries:** Navigate to the **Custom Folders** tab, click **Select SFX Folder**, and choose any folder on your hard drive containing `.wav`, `.mp3`, `.ogg`, or `.m4a` files.
2. **Browse & Filter:** Switch back to the **Library** tab. Use the auto-generated category buttons or the search bar to find sounds instantly.
3. **Preview & Adjust:** Click any sound card to preview it. Adjust playback speed (`0.5x` to `2.0x`) and volume, or toggle the **Loop** button.
4. **Drop onto Timeline:**
   - **Double-click** the sound card, or
   - Click the **"Add to Timeline"** button in the footer player.
   - The audio file will be imported into your project bin and automatically placed at your playhead position (CTI) on the first non-overlapping audio track.
5. **Manage Favorites:** Click the **star icon** on any sound card to save it to your Favorites tab.
6. **Access Settings:** Click the **gear icon** in the bottom-left corner to customize your theme, toggle folder display options, or click **"Open Settings Folder"** to open your persistent configuration folder in Finder / File Explorer.
---
## 💾 Where are Settings Stored?
All preferences, theme choices, folder links, and favorites are stored in a clean JSON file outside Adobe's volatile cache:
- **macOS:** `~/Documents/hub.wav/settings.json`
- **Windows:** `C:\Users\<Your-Username>\Documents\hub.wav\settings.json`
This ensures your entire setup remains safe and persistent across cache cleanups, re-installations, and Adobe Creative Cloud version updates.
