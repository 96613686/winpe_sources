# GetOSVersionFromFile

- ea: `0x18009d1d4`
- end: `0x18009d3c0`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800a45f0`

## callees

- `0x180008570`
- `0x180011c5c`
- `0x18009d1d4`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x18009d238`
- `KERNEL32!GetSystemDirectoryW` at `0x18009d27f`
- `KERNEL32!GetSystemDirectoryW` at `0x18009d238`
- `KERNEL32!GetSystemDirectoryW` at `0x18009d27f`
- `KERNEL32!GetFileAttributesW` at `0x18009d26d`
- `KERNEL32!GetFileAttributesW` at `0x18009d26d`
- `KERNEL32!GetProcessHeap` at `0x18009d2c4`
- `KERNEL32!GetProcessHeap` at `0x18009d2c4`
- `KERNEL32!HeapAlloc` at `0x18009d2e1`
- `KERNEL32!HeapAlloc` at `0x18009d2e1`
- `KERNEL32!HeapFree` at `0x18009d38e`
- `KERNEL32!HeapFree` at `0x18009d38e`
- `VERSION!GetFileVersionInfoSizeW` at `0x18009d2b3`
- `VERSION!GetFileVersionInfoSizeW` at `0x18009d2b3`
- `VERSION!GetFileVersionInfoW` at `0x18009d306`
- `VERSION!GetFileVersionInfoW` at `0x18009d306`
- `VERSION!VerQueryValueW` at `0x18009d32b`
- `VERSION!VerQueryValueW` at `0x18009d32b`

## string_xrefs

- `0x18009d24b`: `\kernel32.dll`
- `0x18009d28f`: `\ntdll.dll`

## pseudocode

```c

```
