# GetLongPathNameW

- ea: `0x180076630`
- end: `0x180076d9c`
- name: `GetLongPathNameW`
- size: `1900`
- prototype: `DWORD __stdcall(LPCWSTR lpszShortPath, LPWSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180077f90`
- `0x18013d720`

## callees

- `0x180015d70`
- `0x180076630`
- `0x180076e30`
- `0x180077510`
- `0x180077680`
- `0x1800777f0`
- `0x18012d119`
- `0x18012eecc`
- `0x180188ec5`
- `0x180188f10`

## import_xrefs

- `ntdll!wcslen` at `0x18007683a`
- `ntdll!wcslen` at `0x180076a61`
- `ntdll!wcslen` at `0x180076c42`
- `ntdll!wcslen` at `0x180076ce5`
- `ntdll!wcslen` at `0x18007683a`
- `ntdll!wcslen` at `0x180076a61`
- `ntdll!wcslen` at `0x180076c42`
- `ntdll!wcslen` at `0x180076ce5`
- `ntdll!RtlSetLastWin32Error` at `0x180076b0e`
- `ntdll!RtlSetLastWin32Error` at `0x180076c89`
- `ntdll!RtlSetLastWin32Error` at `0x180076d92`
- `ntdll!RtlSetLastWin32Error` at `0x180076b0e`
- `ntdll!RtlSetLastWin32Error` at `0x180076c89`
- `ntdll!RtlSetLastWin32Error` at `0x180076d92`
- `ntdll!RtlFreeHeap` at `0x180076d3b`
- `ntdll!RtlFreeHeap` at `0x180076d58`
- `ntdll!RtlFreeHeap` at `0x180189864`
- `ntdll!RtlFreeHeap` at `0x180189883`
- `ntdll!RtlFreeHeap` at `0x180076d3b`
- `ntdll!RtlFreeHeap` at `0x180076d58`
- `ntdll!RtlFreeHeap` at `0x180189864`
- `ntdll!RtlFreeHeap` at `0x180189883`
- `ntdll!RtlAllocateHeap` at `0x180076af9`
- `ntdll!RtlAllocateHeap` at `0x180076c6a`
- `ntdll!RtlAllocateHeap` at `0x180076af9`
- `ntdll!RtlAllocateHeap` at `0x180076c6a`

## pseudocode

```c

```
