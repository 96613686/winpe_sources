# FindFirstStreamW

- ea: `0x180079210`
- end: `0x180079522`
- name: `FindFirstStreamW`
- size: `786`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, STREAM_INFO_LEVELS InfoLevel, LPVOID lpFindStreamData, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callees

- `0x1800134a0`
- `0x180077510`
- `0x180079210`
- `0x180079530`
- `0x180188eb9`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800793b4`
- `ntdll!NtQueryInformationFile` at `0x1800793b4`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18007926e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18007926e`
- `ntdll!NtCreateFile` at `0x180079318`
- `ntdll!NtCreateFile` at `0x180079318`
- `ntdll!RtlSetLastWin32Error` at `0x180190d34`
- `ntdll!RtlSetLastWin32Error` at `0x180190d34`
- `ntdll!NtClose` at `0x180079510`
- `ntdll!NtClose` at `0x18018990e`
- `ntdll!NtClose` at `0x180079510`
- `ntdll!NtClose` at `0x18018990e`
- `ntdll!RtlFreeHeap` at `0x18007936f`
- `ntdll!RtlFreeHeap` at `0x180079492`
- `ntdll!RtlFreeHeap` at `0x1800794fe`
- `ntdll!RtlFreeHeap` at `0x1801898ef`
- `ntdll!RtlFreeHeap` at `0x18018992d`
- `ntdll!RtlFreeHeap` at `0x18007936f`
- `ntdll!RtlFreeHeap` at `0x180079492`
- `ntdll!RtlFreeHeap` at `0x1800794fe`
- `ntdll!RtlFreeHeap` at `0x1801898ef`
- `ntdll!RtlFreeHeap` at `0x18018992d`
- `ntdll!RtlAllocateHeap` at `0x180079387`
- `ntdll!RtlAllocateHeap` at `0x180079387`

## pseudocode

```c

```
