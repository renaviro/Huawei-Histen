Huawei Histen — Port of Huawei Original Audio Engines to Android [Mate 80 Pro]​  

Requirements: Android 14 or later · ARM64 architecture
Root access is NOT required for installation and operation.

I'm developing a port of Huawei Histen that brings Huawei's original audio processing technology to Android, enabling system-wide audio processing.

The project uses original Huawei audio libraries, factory tuning parameters and spatial audio tables. A custom audio pipeline has been developed to capture system audio, process it through Huawei's DSP engines and route the processed sound back to your headphones.

🎧 Audio Engines & Sound Effects​
HVS​
Huawei's original audio processing engine, featuring spatial audio processing and advanced frequency filtering.

The port includes Huawei's factory sound profiles: Fidelity, Music, Movie, Book and Low Power. It also allows users to fine-tune available frequency bands and preamp levels.

The engine features:

10-band equalizer covering 31 Hz to 16 kHz;
Original Huawei sound presets;
Four spatial 3D audio modes;
DRC (Dynamic Range Compression) for dynamic range control;
Limiter for preventing audio clipping and excessive peaks.
SpaceRender​
A separate Huawei spatial audio renderer featuring an original processing table designed to create an immersive soundstage around the listener.

Three processing modes are available. These features were previously available only on Huawei smartphones and selected Huawei FreeBuds Pro headphones.

Head tracking is not yet implemented. Spatial processing currently operates without scene adjustments based on headphone motion sensors.

The application currently includes some additional parameters that are not available in Huawei's original application. As development progresses, some of these parameters will be adapted or removed.

🔌 Connection Methods​
Two independent methods of obtaining privileged access are available:

Shizuku — runs audio processing through the authorized Shizuku service.
ADB TCP — connects the application to the device's ADB service over TCP and launches its own component. If ADB TCP is already enabled and authorized, there is no need to reconnect through a PC.
ADB TCP is the recommended connection method.

To connect, enter the following commands in a terminal to enable privileged access for the application. Access remains available until the phone is rebooted.

Code:
adb devices
adb tcpip

A video tutorial on how to connect to ADB TCP within the app itself. The program has three operating status: “off” — when the engine is not active; “waiting” — when the engine is on and waiting for a sound source; “on” — when it works on with headphones and a Bluetooth headset.

Audio capture and DSP processing are performed directly on the phone.

🔊 Audio Capture Methods​
PLAYBACK / Audio Policy Loopback — captures currently playing audio while excluding Histen's own output stream.
OUTPUT / REMOTE_SUBMIX — an alternative system audio capture method, retained for comparison and compatibility.
Important: Processed audio can be routed back to Bluetooth, wired and USB headphones.

⚙️ Additional Features​
Always-on PCM adapter with original Huawei audio conversion functions.
Smooth application of DSP settings.
Automatic headphone detection and audio processing recovery after reconnection.
Automatic ADB connection recovery attempts.
Diagnostics for audio routing, signal levels and errors.
📱 Compatibility & Project Status​
Android 14 and later · ARM64 architecture.


Primary testing is being conducted on the Samsung Galaxy S25 Ultra running Android 17.

The project is actively under development.
