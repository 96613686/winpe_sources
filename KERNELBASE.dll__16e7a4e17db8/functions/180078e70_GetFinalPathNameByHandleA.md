# GetFinalPathNameByHandleA

- ea: `0x180078e70`
- end: `0x180078fdc`
- name: `GetFinalPathNameByHandleA`
- size: `364`
- prototype: `DWORD __stdcall(HANDLE hFile, LPSTR lpszFilePath, DWORD cchFilePath, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callees

- `0x180077f90`
- `0x180078e70`
- `0x180188eb9`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x180078f65`
- `ntdll!RtlFreeAnsiString` at `0x180078f65`
- `ntdll!wcslen` at `0x180078f09`
- `ntdll!wcslen` at `0x180078f09`
- `ntdll!RtlSetLastWin32Error` at `0x180078fd4`
- `ntdll!RtlSetLastWin32Error` at `0x180078fd4`
- `ntdll!RtlFreeHeap` at `0x180078f7d`
- `ntdll!RtlFreeHeap` at `0x180078fa8`
- `ntdll!RtlFreeHeap` at `0x180078fc4`
- `ntdll!RtlFreeHeap` at `0x180078f7d`
- `ntdll!RtlFreeHeap` at `0x180078fa8`
- `ntdll!RtlFreeHeap` at `0x180078fc4`
- `ntdll!RtlAllocateHeap` at `0x180078eca`
- `ntdll!RtlAllocateHeap` at `0x180078eca`

## pseudocode

```c

```
