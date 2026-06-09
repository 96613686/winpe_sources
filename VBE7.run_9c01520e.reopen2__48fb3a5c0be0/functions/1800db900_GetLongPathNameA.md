# GetLongPathNameA

- ea: `0x1800db900`
- end: `0x1800dbcb9`
- name: `GetLongPathNameA`
- size: `953`
- prototype: `DWORD __stdcall(LPCSTR lpszShortPath, LPSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007ee68`

## callees

- `0x18001ce60`
- `0x1800db900`
- `0x1800dbcc0`
- `0x1800dbd80`
- `0x180379380`
- `0x180379520`
- `0x1803796a6`

## import_xrefs

- `MSVCR100!free` at `0x1800dbc81`
- `MSVCR100!free` at `0x1800dbc81`
- `MSVCR100!malloc` at `0x1800dbac4`
- `MSVCR100!malloc` at `0x1800dbac4`
- `KERNEL32!lstrlenA` at `0x1800dbbc6`
- `KERNEL32!lstrlenA` at `0x1800dbbc6`
- `KERNEL32!RaiseException` at `0x1800db988`
- `KERNEL32!RaiseException` at `0x1800dba86`
- `KERNEL32!RaiseException` at `0x1800dbaf6`
- `KERNEL32!RaiseException` at `0x1800dbb46`
- `KERNEL32!RaiseException` at `0x1800dbbed`
- `KERNEL32!RaiseException` at `0x1800db988`
- `KERNEL32!RaiseException` at `0x1800dba86`
- `KERNEL32!RaiseException` at `0x1800dbaf6`
- `KERNEL32!RaiseException` at `0x1800dbb46`
- `KERNEL32!RaiseException` at `0x1800dbbed`
- `KERNEL32!lstrcpyA` at `0x1800dbbb8`
- `KERNEL32!lstrcpyA` at `0x1800dbbb8`
- `KERNEL32!FindFirstFileA` at `0x1800dbb90`
- `KERNEL32!FindFirstFileA` at `0x1800dbb90`
- `KERNEL32!FindClose` at `0x1800dbba5`
- `KERNEL32!FindClose` at `0x1800dbba5`

## pseudocode

```c

```
