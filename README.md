# Process Injection & Memory Forensics

## Overview

A controlled cybersecurity lab demonstrating user-mode process
injection and memory forensics using Cheat Engine and Volatility 3.

## Environment

- Target: Windows 10/11 VM
- Analysis Machine: Kali Linux
- Injection Tool: Cheat Engine
- Memory Acquisition: WinPmem
- Forensics: Volatility 3

## Methodology

1. Started Notepad in an isolated Windows VM.
2. Used Cheat Engine to allocate and modify memory.
3. Created a controlled executable/writable memory region.
4. Acquired a memory dump.
5. Transferred the dump to Kali Linux.
6. Analyzed the dump using Volatility 3.
7. Identified the Notepad process using `windows.pslist`.
8. Used `windows.malfind` to identify suspicious memory.
9. Analyzed the suspicious memory region and protection flags.
10. Correlated the forensic findings with the controlled injection.

## Key Finding

Volatility 3 identified a suspicious
`PAGE_EXECUTE_READWRITE` region in `notepad.exe`.

The controlled test bytes included:

`90 90 90 90 C3`

The suspicious memory address was correlated with the region
created during the controlled injection exercise.

## Tools

- Cheat Engine
- WinPmem
- Volatility 3
- Kali Linux
- Windows 10/11

## Evidence

Detailed screenshots and the final report are available in
the `Screenshots` and `Report` directories.

## Disclaimer

This project was performed exclusively in an isolated,
authorized cybersecurity training environment.
