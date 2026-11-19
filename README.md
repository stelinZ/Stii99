# Sony Pods — WF-1000XM5 connection card for Android

A lightweight Android app prototype for Sony WF-1000XM5 with a custom animated connection card, battery display, device selection and a foreground Bluetooth monitoring service.

## Build APK

The repository includes a GitHub Actions workflow:

1. Create a GitHub repository and upload the contents of this project.
2. Open **Actions → Build Sony Pods APK → Run workflow** (or push to `main`/`master`).
3. Download `app-debug.apk` from the workflow run's **Artifacts**, or use the latest GitHub Release.
4. Install the APK on the phone and open Sony Pods.

## First-time setup

1. Grant **Nearby devices / Bluetooth** permission.
2. Grant **Display over other apps** permission for the floating connection card.
3. Select the paired WF-1000XM5 (or leave automatic selection enabled).
4. Use **Проверить анимацию** to preview the card.

## Important compatibility note

The custom case/earbud artwork and animations are local Canvas drawings; they do not require network access or a 3D engine. Battery data is a separate concern: Android's public Bluetooth APIs do not consistently expose independent left/right/case values. `SonyReader.kt` is explicitly experimental and its private Sony RFCOMM framing has not been validated against a physical WF-1000XM5 in this project. A missing value is shown as `—`; demo values are used only in the preview button. Close Sony Sound Connect during protocol testing because another client may hold the control connection.

This project does not claim to be an Apple product and does not use Apple's proprietary artwork or branding.