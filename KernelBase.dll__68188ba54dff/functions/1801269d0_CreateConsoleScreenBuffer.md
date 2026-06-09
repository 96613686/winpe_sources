# CreateConsoleScreenBuffer

- ea: `0x1801269d0`
- end: `0x180126c6d`
- name: `CreateConsoleScreenBuffer`
- size: `669`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, DWORD dwShareMode, const SECURITY_ATTRIBUTES *lpSecurityAttributes, DWORD dwFlags, LPVOID lpScreenBufferData)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800dbf68`
- `0x1801269d0`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180126b36`
- `ntdll!RtlInitUnicodeString` at `0x180126b36`
- `ntdll!NtCreateFile` at `0x180126ba1`
- `ntdll!NtCreateFile` at `0x180126ba1`
- `ntdll!RtlSetLastWin32Error` at `0x180126c0c`
- `ntdll!RtlSetLastWin32Error` at `0x180126c43`
- `ntdll!RtlSetLastWin32Error` at `0x180126c0c`
- `ntdll!RtlSetLastWin32Error` at `0x180126c43`
- `ntdll!RtlNtStatusToDosError` at `0x180126c04`
- `ntdll!RtlNtStatusToDosError` at `0x180126c3b`
- `ntdll!RtlNtStatusToDosError` at `0x180126c04`
- `ntdll!RtlNtStatusToDosError` at `0x180126c3b`
- `ntdll!NtClose` at `0x180126c17`
- `ntdll!NtClose` at `0x180126c17`
- `ntdll!RtlFreeHeap` at `0x180126bc4`
- `ntdll!RtlFreeHeap` at `0x180126bc4`
- `ntdll!RtlAllocateHeap` at `0x180126aa8`
- `ntdll!RtlAllocateHeap` at `0x180126aa8`

## pseudocode

```c

```
