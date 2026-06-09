# CMsiFileCopy::OpenSource(bool)

- ea: `0x180080934`
- end: `0x180080cc8`
- name: `?OpenSource@CMsiFileCopy@@IEAAPEAVIMsiRecord@@_N@Z`
- size: `916`
- prototype: `struct IMsiRecord *__fastcall(CMsiFileCopy *__hidden this, bool)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x18007fb70`
- `0x180080934`

## callees

- `0x180025a18`
- `0x180026ffc`
- `0x18007fa28`
- `0x180080934`
- `0x180080d7c`
- `0x180083178`
- `0x1800833ec`
- `0x180123598`
- `0x18013a830`
- `0x18014148c`
- `0x18014e4d4`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180080afc`
- `KERNEL32!CloseHandle` at `0x180080b7d`
- `KERNEL32!CloseHandle` at `0x180080afc`
- `KERNEL32!CloseHandle` at `0x180080b7d`
- `KERNEL32!GetLastError` at `0x180080a97`
- `KERNEL32!GetLastError` at `0x180080b92`
- `KERNEL32!GetLastError` at `0x180080a97`
- `KERNEL32!GetLastError` at `0x180080b92`
- `KERNEL32!SetLastError` at `0x180080b08`
- `KERNEL32!SetLastError` at `0x180080b8c`
- `KERNEL32!SetLastError` at `0x180080b08`
- `KERNEL32!SetLastError` at `0x180080b8c`
- `KERNEL32!CreateFileW` at `0x180080a6e`
- `KERNEL32!CreateFileW` at `0x180080a6e`
- `KERNEL32!GetFileType` at `0x180080b17`
- `KERNEL32!GetFileType` at `0x180080b17`

## string_xrefs

- `0x180080b40`: `Error: This is not a valid file, hence failing to create: %s`
- `0x180080abf`: `Error: This file path is updated, hence failing to create: %s`

## pseudocode

```c

```
