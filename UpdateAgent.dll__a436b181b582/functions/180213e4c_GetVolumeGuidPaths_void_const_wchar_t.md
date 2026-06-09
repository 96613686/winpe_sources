# GetVolumeGuidPaths(void * const,wchar_t * *)

- ea: `0x180213e4c`
- end: `0x180214490`
- name: `?GetVolumeGuidPaths@@YAJQEAXPEAPEA_W@Z`
- size: `1604`
- prototype: `__int64 __fastcall(void *const, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180212d40`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180006a18`
- `0x180007000`
- `0x18008b360`
- `0x18008b38c`
- `0x18008b3ec`
- `0x180093308`
- `0x180213764`
- `0x180213e4c`
- `0x18029ea8c`

## import_xrefs

- `ntdll!NtClose` at `0x180214106`
- `ntdll!NtClose` at `0x180214138`
- `ntdll!NtClose` at `0x180214179`
- `ntdll!NtClose` at `0x180214283`
- `ntdll!NtClose` at `0x1802142f4`
- `ntdll!NtClose` at `0x180214355`
- `ntdll!NtClose` at `0x1802143b6`
- `ntdll!NtClose` at `0x180214417`
- `ntdll!NtClose` at `0x18021446a`
- `ntdll!NtClose` at `0x180214106`
- `ntdll!NtClose` at `0x180214138`
- `ntdll!NtClose` at `0x180214179`
- `ntdll!NtClose` at `0x180214283`
- `ntdll!NtClose` at `0x1802142f4`
- `ntdll!NtClose` at `0x180214355`
- `ntdll!NtClose` at `0x1802143b6`
- `ntdll!NtClose` at `0x180214417`
- `ntdll!NtClose` at `0x18021446a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021402a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021402a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802140b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802140b1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18021409b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18021409b`

## string_xrefs

- `0x18021400b`: `\\.\MountPointManager`

## pseudocode

```c

```
