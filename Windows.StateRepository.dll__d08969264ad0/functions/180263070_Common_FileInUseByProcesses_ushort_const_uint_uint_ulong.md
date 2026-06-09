# Common::FileInUseByProcesses(ushort const *,uint,uint *,ulong *)

- ea: `0x180263070`
- end: `0x18026318b`
- name: `?FileInUseByProcesses@Common@@YAJPEBGIPEAIPEAK@Z`
- size: `283`
- prototype: `ULONG __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180263264`

## callees

- `0x18018f650`
- `0x180263070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802630e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802630e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18026311b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18026311b`
- `ntdll!NtQueryInformationFile` at `0x180263110`
- `ntdll!NtQueryInformationFile` at `0x180263110`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180263127`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180263127`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802630d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802630d6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18026309d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18026309d`

## pseudocode

```c

```
