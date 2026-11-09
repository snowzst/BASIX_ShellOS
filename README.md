 <p align="center">
  <img src="assets/ShellLogo.png" width="120"/>
</p>

<h1 align="center">ShellOS</h1>

<p align="center">
  A minimal operating system built from scratch in Assembly and C,<br>
  with Rust modules and an interactive shell.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-green"/>
  <img src="https://img.shields.io/badge/languages-Assembly%20%7C%20C%20%7C%20Rust-blue"/>
  <img src="https://img.shields.io/badge/tested-QEMU-orange"/>
  <img src="https://img.shields.io/badge/status-in%20development-yellow"/>
</p>

---

## About

**ShellOS** is a basic operating system built from scratch for educational purposes.

It features its own bootloader, a kernel called **Basix**, an interactive shell, a RAM-based filesystem, a built-in text editor, a TUI graphical interface, and an installer.

> **Note:** The Basix kernel is a minimal educational kernel inspired by POSIX.
> The project is migrating to Linux as its foundation to further mature the system.

<p align="center">
  <img src="assets/BasixLogo.png" width="80"/>
  <br>
  <i>Basix — the educational kernel powering ShellOS</i>
</p>

---

## Project Structure

| File | Description |
|---------|-----------|
| `bootloader.asm` | x86 Assembly bootloader — initializes the system and loads the kernel |
| `entry.asm` | Kernel entry point — 32-bit entry point |
| `kernel.c` | **Basix** — VGA driver, PS/2 keyboard, scrolling, initialization |
| `shell.c` | Shell loop, input handling, and command parser |
| `commands.c` | Implementation of all shell commands |
| `fs.c` | RAM-based filesystem — volatile directories and files |
| `write.c` | Minimal text editor integrated into the shell |
| `makeux.c` | Windows 1.0-style TUI graphical interface |
| `shinstall.c` | Visual installer with language, keyboard, and partitioning options |
| `keymap.c` | Keyboard layouts — ABNT2, QWERTY US, QWERTZ DE, AZERTY FR |
| `ata.c` | ATA driver — disk read and write operations |
| `partition.c` | Partition manager — writes an MBR partition table to the disk |
| `linker.ld` | Linker script — defines the kernel's memory layout |
| `Makefile` | Build, packaging, and execution |
| `memman/` | Memory management module written in **Rust** |

---

## Available Commands

| Command | Description |
|---------|-----------|
| `help` | Lists all available commands |
| `clear` | Clears the screen |
| `echo <text>` | Prints text to the screen |
| `ls` | Lists directories and files |
| `mkdir <name>` | Creates a directory |
| `rm <dir>/<file>` | Removes a file |
| `write <file>` | Opens the text editor (F2 to save, F10 to exit) |
| `makeux` | Opens the TUI graphical interface |
| `shinstall` | Installs ShellOS to disk |
| `mem` | Displays kernel memory information |
| `ver` | Displays the ShellOS version |
| `halt` | Shuts down the system |

---

## MakeUX — Graphical Interface

| Key | Action |
|-------|------|
| `F1` | Return to the shell |
| `F2` | View files |
| `F3` | Display memory information |
| `F10` | Exit MakeUX |
| `F12` | Shut down the system |

---

## Supported Keyboard Layouts

| Layout | Region |
|--------|--------|
| ABNT2 | Portuguese (Brazil) |
| QWERTY | English (US) |
| QWERTZ | German (DE) |
| AZERTY | French (FR) |

---

## Requirements

```bash
sudo apt install nasm gcc make qemu-system-x86 xorriso
```

---

## Building and Running

```bash
# build
make

# test in QEMU (recommended environment)
make run

# generate packages (.img .vdi .iso)
make package
```

---

## Compatibility

| Environment | Status |
|----------|--------|
| QEMU | ✅ Tested and working |
| VirtualBox | ⚠️ Functional, may contain bugs |
| VMware | ⚠️ No guarantees, possible critical failures |
| Real hardware | ⚠️ No guarantees, not recommended |

---

## Technologies

- **x86 Assembly** — bootloader and entry point
- **C** — Basix kernel, shell, and filesystem
- **Rust** — memory management module (`memman`)

---

## Roadmap

- [x] Custom bootloader
- [x] Basix kernel
- [x] Interactive shell
- [x] RAM-based filesystem
- [x] Text editor
- [x] TUI graphical interface (MakeUX)
- [x] Installer (ShInstall)
- [x] ATA driver
- [x] Keyboard layouts
- [ ] Migration to the Linux kernel
- [ ] Networking
- [ ] Persistent filesystem
- [ ] Full MakeUX implementation

---

## License

MIT — free to use, modify, and distribute.

Anyone can fork the project and distribute their own version for free.

---

## Disclaimer

This project was built with the assistance of AI as a learning tool, similar to the use of technical documentation and the OSDev Wiki.

Developed on **Linux Mint** using **Visual Studio Code**.

---

## Additional Note

The author of this project is a **student** of programming and Linux.

Please be patient with any potential errors!
