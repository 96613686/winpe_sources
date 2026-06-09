# IsolationAwareLoadLibraryExW

- ea: `0x18011ae3c`
- end: `0x18011af15`
- name: `IsolationAwareLoadLibraryExW`
- size: `217`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18011b8c0`

## callees

- `0x1800016b0`
- `0x18011ae3c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18011aed7`
- `KERNEL32!GetLastError` at `0x180380c32`
- `KERNEL32!GetLastError` at `0x18011aed7`
- `KERNEL32!GetLastError` at `0x180380c32`
- `KERNEL32!SetLastError` at `0x18011aef6`
- `KERNEL32!SetLastError` at `0x180380c50`
- `KERNEL32!SetLastError` at `0x18011aef6`
- `KERNEL32!SetLastError` at `0x180380c50`
- `KERNEL32!OutputDebugStringA` at `0x18011ae77`
- `KERNEL32!OutputDebugStringA` at `0x18011ae77`
- `KERNEL32!ActivateActCtx` at `0x18011ae9c`
- `KERNEL32!ActivateActCtx` at `0x18011ae9c`
- `KERNEL32!DeactivateActCtx` at `0x18011aeea`
- `KERNEL32!DeactivateActCtx` at `0x180380c44`
- `KERNEL32!DeactivateActCtx` at `0x18011aeea`
- `KERNEL32!DeactivateActCtx` at `0x180380c44`
- `KERNEL32!LoadLibraryExW` at `0x18011aebd`
- `KERNEL32!LoadLibraryExW` at `0x18011aebd`

## pseudocode

```c

```
