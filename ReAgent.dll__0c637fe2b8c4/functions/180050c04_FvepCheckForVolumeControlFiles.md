# FvepCheckForVolumeControlFiles

- ea: `0x180050c04`
- end: `0x180050e9c`
- name: `FvepCheckForVolumeControlFiles`
- size: `664`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180051660`

## callees

- `0x180006e84`
- `0x180006ed8`
- `0x18004cae4`
- `0x180050a28`
- `0x180050a98`
- `0x180050c04`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180050cb4`
- `KERNEL32!GetLastError` at `0x180050e65`
- `KERNEL32!GetLastError` at `0x180050cb4`
- `KERNEL32!GetLastError` at `0x180050e65`
- `KERNEL32!CloseHandle` at `0x180050e75`
- `KERNEL32!CloseHandle` at `0x180050e75`
- `KERNEL32!DeviceIoControl` at `0x180050caa`
- `KERNEL32!DeviceIoControl` at `0x180050caa`
- `KERNEL32!GetFileAttributesW` at `0x180050e1e`
- `KERNEL32!GetFileAttributesW` at `0x180050e39`
- `KERNEL32!GetFileAttributesW` at `0x180050e1e`
- `KERNEL32!GetFileAttributesW` at `0x180050e39`
- `ADVAPI32!SetThreadToken` at `0x180050e5b`
- `ADVAPI32!SetThreadToken` at `0x180050e5b`

## pseudocode

```c

```
