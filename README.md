# ClamshellLock

<p>
  <img src="icon.png" alt="ClamshellLock app icon" width="128">
</p>





A small native macOS menu bar app that locks a MacBook when its lid closes while an external display is connected.

## Features

- Detects external displays locally.
- Monitors the MacBook lid state.
- Sends macOS's built-in Control-Command-Q lock shortcut.
- Shows external-display status in the menu bar.
- Uses no network connection, analytics, or background service.
- Uses the existing app icon embedded in the application bundle.
- Automatic locking is always enabled when an external display is connected.



## Requirements

- A MacBook running a recent version of macOS.
- An external display.
- Accessibility permission for ClamshellLock.
- For reliable clamshell mode, connect the MacBook to power and use an external keyboard or mouse.

## Install

1. Download `ClamshellLock-macOS.zip` from the repository root or the GitHub Releases page.
2. Unzip the downloaded file.
3. Move `ClamshellLock.app` to the Applications folder.
4. Open ClamshellLock.
5. Open **System Settings > Privacy & Security > Accessibility**.
6. Enable **ClamshellLock**.
7. Keep the app running. It stays in the menu bar.
8. Connect an external display and close the MacBook lid. The Mac will lock automatically.

## First launch

This release is not notarized by Apple. If macOS shows a security warning:

1. Right-click `ClamshellLock.app` and choose **Open**.
2. If it is still blocked, open **System Settings > Privacy & Security** and click **Open Anyway**.

Only download releases from a source you trust.

## Usage

- With an external display connected, ClamshellLock monitors the lid state.
- When the lid changes from open to closed, the app locks the screen.
- When no external display is connected, automatic lid locking is inactive.
- The app must remain running for monitoring to work.
- To start it automatically, add ClamshellLock under **System Settings > General > Login Items**.

## Build from source

Requirements: Xcode Command Line Tools and Swift.

```sh
cd ClamshellLock
./build-app.sh
```

The script creates `ClamshellLock.app` in the project directory.


## Privacy and permissions

ClamshellLock does not use the network or collect data. Accessibility permission is used only to send the standard macOS lock-screen shortcut. Display and lid state are read locally.

## Limitations

- Lid-state reading may be unavailable on non-MacBook hardware, virtual machines, or unsupported macOS versions.
- The app does not change macOS sleep settings or prevent sleep.
- The app is ad-hoc signed and not Apple-notarized; macOS may show a first-launch warning.
