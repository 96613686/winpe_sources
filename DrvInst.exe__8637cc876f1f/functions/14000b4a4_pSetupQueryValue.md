# pSetupQueryValue

- ea: `0x14000b4a4`
- end: `0x14000b5e9`
- name: `pSetupQueryValue`
- size: `325`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCWSTR SourceString@<rdx>, __int64)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000a86c`
- `0x14000a94c`
- `0x14000b3d0`
- `0x14000d644`
- `0x14000d6d8`
- `0x14000d7b4`
- `0x14000d98c`
- `0x140021f50`
- `0x140024650`

## callees

- `0x14000b4a4`
- `0x140045ed2`
- `0x140045f30`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x14000b551`
- `ntdll!NtQueryValueKey` at `0x14000b551`
- `ntdll!RtlInitUnicodeString` at `0x14000b52c`
- `ntdll!RtlInitUnicodeString` at `0x14000b52c`
- `ntdll!RtlNtStatusToDosError` at `0x14000b56c`
- `ntdll!RtlNtStatusToDosError` at `0x14000b56c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b504`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b504`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b5c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b5c5`

## pseudocode

```c

```
