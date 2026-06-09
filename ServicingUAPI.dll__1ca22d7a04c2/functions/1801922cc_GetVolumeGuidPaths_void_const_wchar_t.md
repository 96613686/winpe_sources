# GetVolumeGuidPaths(void * const,wchar_t * *)

- ea: `0x1801922cc`
- end: `0x180192910`
- name: `?GetVolumeGuidPaths@@YAJQEAXPEAPEA_W@Z`
- size: `1604`
- prototype: `__int64 __fastcall(void *const, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1801911c0`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x180006840`
- `0x18000ba14`
- `0x18000ba40`
- `0x1800296a4`
- `0x18003bdb4`
- `0x180191be4`
- `0x1801922cc`
- `0x1801b324c`

## import_xrefs

- `ntdll!NtClose` at `0x180192586`
- `ntdll!NtClose` at `0x1801925b8`
- `ntdll!NtClose` at `0x1801925f9`
- `ntdll!NtClose` at `0x180192703`
- `ntdll!NtClose` at `0x180192774`
- `ntdll!NtClose` at `0x1801927d5`
- `ntdll!NtClose` at `0x180192836`
- `ntdll!NtClose` at `0x180192897`
- `ntdll!NtClose` at `0x1801928ea`
- `ntdll!NtClose` at `0x180192586`
- `ntdll!NtClose` at `0x1801925b8`
- `ntdll!NtClose` at `0x1801925f9`
- `ntdll!NtClose` at `0x180192703`
- `ntdll!NtClose` at `0x180192774`
- `ntdll!NtClose` at `0x1801927d5`
- `ntdll!NtClose` at `0x180192836`
- `ntdll!NtClose` at `0x180192897`
- `ntdll!NtClose` at `0x1801928ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192531`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801924aa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801924aa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019251b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019251b`

## string_xrefs

- `0x18019248b`: `\\.\MountPointManager`

## pseudocode

```c

```
