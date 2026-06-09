# SiSetDriveMaintenance(_GUID *,uchar,ulong,_SU_DRIVE_OBJECT *)

- ea: `0x1801b1b1c`
- end: `0x1801b1dd3`
- name: `?SiSetDriveMaintenance@@YAHPEAU_GUID@@EKPEAU_SU_DRIVE_OBJECT@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int8, unsigned int, struct _SU_DRIVE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1801b1280`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x18000ce3c`
- `0x180195a90`
- `0x1801b1b1c`
- `0x1801b42a8`
- `0x1801b43c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1cff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b1bae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b1dab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b1bae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b1dab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b1b99`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b1d0d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b1b99`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b1d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b1d9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b1d9e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b1c9c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b1cec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b1c9c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b1cec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b1c54`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b1c54`

## string_xrefs

- `0x1801b1c65`: `CreateFile`

## pseudocode

```c

```
