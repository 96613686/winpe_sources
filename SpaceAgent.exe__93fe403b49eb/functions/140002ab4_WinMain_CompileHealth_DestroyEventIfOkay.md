# WinMain_CompileHealth_DestroyEventIfOkay

- ea: `0x140002ab4`
- end: `0x140002b8f`
- name: `WinMain_CompileHealth_DestroyEventIfOkay`
- size: `219`
- prototype: `__int64 __fastcall(HANDLE hMutex, HANDLE *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002868`

## callees

- `0x140002ab4`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x140002b48`
- `KERNEL32!ResetEvent` at `0x140002b48`
- `KERNEL32!ReleaseMutex` at `0x140002b5b`
- `KERNEL32!ReleaseMutex` at `0x140002b5b`
- `KERNEL32!CloseHandle` at `0x140002b19`
- `KERNEL32!CloseHandle` at `0x140002b19`
- `KERNEL32!SetLastError` at `0x140002af1`
- `KERNEL32!SetLastError` at `0x140002b3d`
- `KERNEL32!SetLastError` at `0x140002b7c`
- `KERNEL32!SetLastError` at `0x140002af1`
- `KERNEL32!SetLastError` at `0x140002b3d`
- `KERNEL32!SetLastError` at `0x140002b7c`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002ad5`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002b01`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002ad5`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002b01`
- `KERNEL32!GetLastError` at `0x140002b28`
- `KERNEL32!GetLastError` at `0x140002b50`
- `KERNEL32!GetLastError` at `0x140002b67`
- `KERNEL32!GetLastError` at `0x140002b28`
- `KERNEL32!GetLastError` at `0x140002b50`
- `KERNEL32!GetLastError` at `0x140002b67`

## pseudocode

```c

```
