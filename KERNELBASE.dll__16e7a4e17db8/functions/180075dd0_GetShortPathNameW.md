# GetShortPathNameW

- ea: `0x180075dd0`
- end: `0x18007626c`
- name: `GetShortPathNameW`
- size: `1180`
- prototype: `DWORD __stdcall(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x180015d70`
- `0x180042020`
- `0x180075dd0`
- `0x180076280`
- `0x180076e30`
- `0x180077510`
- `0x180077680`
- `0x1800777f0`
- `0x18012d119`
- `0x18012eecc`
- `0x180188ec5`
- `0x180188f10`

## import_xrefs

- `ntdll!wcslen` at `0x180075e90`
- `ntdll!wcslen` at `0x180075ed5`
- `ntdll!wcslen` at `0x180076013`
- `ntdll!wcslen` at `0x180076097`
- `ntdll!wcslen` at `0x180075e90`
- `ntdll!wcslen` at `0x180075ed5`
- `ntdll!wcslen` at `0x180076013`
- `ntdll!wcslen` at `0x180076097`
- `ntdll!RtlSetLastWin32Error` at `0x180075f1b`
- `ntdll!RtlSetLastWin32Error` at `0x18007616f`
- `ntdll!RtlSetLastWin32Error` at `0x180076248`
- `ntdll!RtlSetLastWin32Error` at `0x180075f1b`
- `ntdll!RtlSetLastWin32Error` at `0x18007616f`
- `ntdll!RtlSetLastWin32Error` at `0x180076248`
- `ntdll!RtlFreeHeap` at `0x180076210`
- `ntdll!RtlFreeHeap` at `0x180076264`
- `ntdll!RtlFreeHeap` at `0x180189804`
- `ntdll!RtlFreeHeap` at `0x180189823`
- `ntdll!RtlFreeHeap` at `0x180076210`
- `ntdll!RtlFreeHeap` at `0x180076264`
- `ntdll!RtlFreeHeap` at `0x180189804`
- `ntdll!RtlFreeHeap` at `0x180189823`
- `ntdll!RtlAllocateHeap` at `0x180075f02`
- `ntdll!RtlAllocateHeap` at `0x180076156`
- `ntdll!RtlAllocateHeap` at `0x180075f02`
- `ntdll!RtlAllocateHeap` at `0x180076156`

## pseudocode

```c

```
