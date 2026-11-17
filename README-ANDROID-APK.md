# BGMI Tournament App — Android APK build

This archive adds a Vite + Capacitor build setup and GitHub Actions workflow around the supplied React/Firebase source.

## Generate the APK with GitHub Actions

1. Extract this ZIP.
2. Upload/commit **all files and folders inside** this extracted folder to your GitHub repository, keeping `.github/workflows/build-android-apk.yml`.
3. In GitHub, open the repository's **Actions** tab and enable Actions if prompted.
4. Select **Build Android APK** → **Run workflow** (or push to `main`/`master`).
5. Wait for the workflow to finish successfully.
6. Open that workflow run and download the `BGMI-Tournament-debug-APK` artifact.
7. Extract the downloaded artifact ZIP; it contains `app-debug.apk`. Transfer it to Android and install it. Android may ask you to allow installation from that browser/file manager.

## Notes

- This creates a **debug APK** for testing and direct installation, not a signed Play Store release.
- The supplied ZIP contained only `App.jsx`, `main.jsx`, `firebase.js`, and `firestore.rules`. This archive adds the missing package manifest, HTML entry point, Vite config, Capacitor config, and workflow.
- The Firebase config is embedded in `firebase.js`. Before real users or entry-fee/prize handling, harden Firestore rules and move trusted wallet/payment operations server-side. The supplied rules permit signed-in users to write match-slot documents, so they are not safe for real-money tournament operations as-is.
- If the workflow fails, share its error log and I can help troubleshoot.
