# Common::FileInUseByProcesses(ushort const *,uint,uint *,ulong *)

- ea: `0x180129788`
- end: `0x1801298cb`
- name: `?FileInUseByProcesses@Common@@YAJPEBGIPEAIPEAK@Z`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800aa820`
- `0x1800aadc4`
- `0x180129af0`

## callees

- `0x1800aed10`
- `0x180129788`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012984e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012984e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801297b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801297b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801297f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801297f4`
- `ntdll!NtQueryInformationFile` at `0x18012983d`
- `ntdll!NtQueryInformationFile` at `0x18012983d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180129860`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180129860`

## pseudocode

```c

```
