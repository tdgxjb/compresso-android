# Compresso Android

Android WebView wrapper skeleton for the CompressO front-end.

This repository contains a minimal Android Studio (Java) project that loads the web UI built from the CompressO repo into a WebView. It is designed as a starting point — copy the production web build (dist/) from the original CompressO project into app/src/main/assets/www/.

Quick start

1. Build the web UI from the original CompressO repository:
   - pnpm install
   - pnpm vite:build
   - locate the build output (typically `dist/`)

2. Copy web assets into this project:
   - mkdir -p app/src/main/assets/www
   - cp -r /path/to/compressO/dist/* app/src/main/assets/www/

3. Open this project in Android Studio and run it on an emulator or device.

Build from command-line

- ./gradlew assembleDebug
- adb install -r app/build/outputs/apk/debug/app-debug.apk

Notes
- Default minSdkVersion is 21. If you need older compatibility, adjust `app/build.gradle` accordingly, but many modern libraries may not support very old Android versions.
- This skeleton does not include native video compression (FFmpeg). To add that, consider ffmpeg-kit and a JS↔Java bridge.
