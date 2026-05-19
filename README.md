# Ubuntu Touch (Halium 11) for Redmi Note 11T 5G (evergo)

This repository contains the GitHub Actions workflow configuration to automatically build Ubuntu Touch (UBports) based on Halium 11 for the **Redmi Note 11T 5G / Redmi Note 11 5G / POCO M4 Pro 5G** (Codename: `evergo` / `evergreen`).

---

## 📱 Device Specifications

| Feature | Specification |
| --- | --- |
| **SoC** | MediaTek Dimensity 810 (6 nm) |
| **CPU** | Octa-core (2x2.4 GHz Cortex-A76 & 6x2.0 GHz Cortex-A55) |
| **GPU** | Mali-G57 MC2 |
| **Released OS** | Android 11, MIUI 12.5 |

---

## 🛠️ Repositories Used in this Build

The build workflow automatically fetches the source trees from the following paths under the user **rnkr344**:

*   **Device Tree:** `https://github.com/rnkr344/android_device_xiaomi_evergo` (Branch: `halium-11.0`)
*   **Kernel Tree:** `https://github.com/rnkr344/android_kernel_xiaomi_evergo` (Branch: `halium-11.0`)
*   **Vendor Tree:** `https://github.com/rnkr344/android_vendor_xiaomi_evergo` (Branch: `halium-11.0`)

---

## 🚀 How to Build via GitHub Actions

You don't need a high-end PC to build this ROM. You can trigger the build directly using GitHub Cloud:

1.  **Fork or Clone** this repository to your own GitHub account.
2.  Make sure your source repositories (`device`, `kernel`, `vendor`) exist on your GitHub account with the `halium-11.0` branch.
3.  Go to the **Actions** tab at the top of this repository.
4.  In the left sidebar, click on **"Ubuntu Touch (Halium 11) Build for Redmi Note 11T 5G"**.
5.  Click the **Run workflow** dropdown button on the right side.
6.  Click the green **Run workflow** button to start the build.

> ⏱️ **Note:** The complete sync and build process can take anywhere between 3 to 5 hours depending on GitHub's runner availability.

---

## 📦 Output Artifacts

Once the build is successfully completed, the workflow will upload the compiled images as build artifacts. You can download them from the summary page of the completed action:

*   `halium-boot.img` (The kernel image for Ubuntu Touch)
*   `system.img` (The Halium system container image)

---

## ⚡ How to Flash (Basic Instructions)

> ⚠️ **Disclaimer:** Flashing custom ROMs can brick your device. Proceed with caution. Backup your data before flashing.

### Prerequisites:
*   Unlocked Bootloader.
*   `fastboot` and `adb` tools installed on your PC.
*   Stock Android 11 firmware installed on the device as a base.

### Flashing Steps:
1. Reboot your phone into **Fastboot Mode** (Volume Down + Power).
2. Connect your phone to the PC via USB.
3. Flash the compiled boot image:
   ```bash
   fastboot flash boot halium-boot.img
   
