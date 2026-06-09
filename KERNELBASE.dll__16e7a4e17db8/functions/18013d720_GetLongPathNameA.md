# GetLongPathNameA

- ea: `0x18013d720`
- end: `0x18013d907`
- name: `GetLongPathNameA`
- size: `487`
- prototype: `DWORD __stdcall(LPCSTR lpszShortPath, LPSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800134a0`
- `0x18006e590`
- `0x180076630`
- `0x18013d720`
- `0x180188ec5`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x18013d8d3`
- `ntdll!RtlFreeAnsiString` at `0x18018cc68`
- `ntdll!RtlFreeAnsiString` at `0x18013d8d3`
- `ntdll!RtlFreeAnsiString` at `0x18018cc68`
- `ntdll!RtlFreeUnicodeString` at `0x18013d8c0`
- `ntdll!RtlFreeUnicodeString` at `0x18018cc56`
- `ntdll!RtlFreeUnicodeString` at `0x18013d8c0`
- `ntdll!RtlFreeUnicodeString` at `0x18018cc56`
- `ntdll!RtlSetLastWin32Error` at `0x18013d777`
- `ntdll!RtlSetLastWin32Error` at `0x18013d83c`
- `ntdll!RtlSetLastWin32Error` at `0x18013d777`
- `ntdll!RtlSetLastWin32Error` at `0x18013d83c`
- `ntdll!RtlFreeHeap` at `0x18013d8fa`
- `ntdll!RtlFreeHeap` at `0x18018cc90`
- `ntdll!RtlFreeHeap` at `0x18013d8fa`
- `ntdll!RtlFreeHeap` at `0x18018cc90`
- `ntdll!RtlAllocateHeap` at `0x18013d810`
- `ntdll!RtlAllocateHeap` at `0x18013d810`

## pseudocode

```c

```
