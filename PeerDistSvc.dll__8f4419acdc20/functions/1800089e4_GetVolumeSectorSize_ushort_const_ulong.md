# GetVolumeSectorSize(ushort const *,ulong *)

- ea: `0x1800089e4`
- end: `0x180008b4a`
- name: `?GetVolumeSectorSize@@YAKPEBGPEAK@Z`
- size: `358`
- prototype: `unsigned int __fastcall(LPCWSTR lpszFileName, LPDWORD lpBytesPerSector)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18003d0b4`
- `0x180053ab8`
- `0x180133548`

## callees

- `0x180008290`
- `0x1800089e4`
- `0x18000cfc0`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ada`
- `KERNEL32!GetVolumePathNameW` at `0x180008a54`
- `KERNEL32!GetVolumePathNameW` at `0x180008a54`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180008ad0`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180008ad0`

## pseudocode

```c

```
