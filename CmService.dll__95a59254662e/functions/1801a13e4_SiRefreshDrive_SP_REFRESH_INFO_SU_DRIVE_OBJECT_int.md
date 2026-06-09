# SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)

- ea: `0x1801a13e4`
- end: `0x1801a163a`
- name: `?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z`
- size: `598`
- prototype: `__int64 __fastcall(struct _SP_REFRESH_INFO *, struct _SU_DRIVE_OBJECT *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18019c180`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x180015370`
- `0x18019d480`
- `0x1801a13e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a156c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a157d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a156c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a157d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a15db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1608`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a15db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1608`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a1497`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a1497`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a15f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a15f5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a14f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a1543`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a14f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a1543`

## string_xrefs

- `0x1801a14ae`: `CreateFile`
- `0x1801a1504`: `SiUpdateProperties`

## pseudocode

```c

```
