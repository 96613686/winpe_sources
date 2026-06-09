# SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)

- ea: `0x1801a1274`
- end: `0x1801a14ca`
- name: `?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z`
- size: `598`
- prototype: `__int64 __fastcall(struct _SP_REFRESH_INFO *, struct _SU_DRIVE_OBJECT *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18019c010`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x180015370`
- `0x18019d310`
- `0x1801a1274`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a13e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a13fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a140d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a13e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a13fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a140d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1425`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a146b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1498`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a146b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1498`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a1327`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a1327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a1485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a1485`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a1382`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a13d3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a1382`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a13d3`

## string_xrefs

- `0x1801a133e`: `CreateFile`
- `0x1801a1394`: `SiUpdateProperties`

## pseudocode

```c

```
