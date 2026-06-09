# GetFinalPathNameByHandleW

- ea: `0x180077f90`
- end: `0x18007882b`
- name: `GetFinalPathNameByHandleW`
- size: `2203`
- prototype: `DWORD __stdcall(HANDLE hFile, LPWSTR lpszFilePath, DWORD cchFilePath, DWORD dwFlags)`
- caller_count: `5`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800481f0`
- `0x180078e70`
- `0x18010d080`
- `0x180150fd0`
- `0x180181d44`

## callees

- `0x1800134a0`
- `0x180042480`
- `0x180074a00`
- `0x180076630`
- `0x180077f90`
- `0x180078834`
- `0x180078b3c`
- `0x180188ec5`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180078153`
- `ntdll!NtQueryInformationFile` at `0x18007840b`
- `ntdll!NtQueryInformationFile` at `0x180078153`
- `ntdll!NtQueryInformationFile` at `0x18007840b`
- `ntdll!wcslen` at `0x18007819d`
- `ntdll!wcslen` at `0x1800781a9`
- `ntdll!wcslen` at `0x1800781bd`
- `ntdll!wcslen` at `0x1800781c9`
- `ntdll!wcslen` at `0x180078210`
- `ntdll!wcslen` at `0x18007821c`
- `ntdll!wcslen` at `0x18007859d`
- `ntdll!wcslen` at `0x1800785a9`
- `ntdll!wcslen` at `0x18007863d`
- `ntdll!wcslen` at `0x180078648`
- `ntdll!wcslen` at `0x1800787ed`
- `ntdll!wcslen` at `0x180078806`
- `ntdll!wcslen` at `0x18007819d`
- `ntdll!wcslen` at `0x1800781a9`
- `ntdll!wcslen` at `0x1800781bd`
- `ntdll!wcslen` at `0x1800781c9`
- `ntdll!wcslen` at `0x180078210`
- `ntdll!wcslen` at `0x18007821c`
- `ntdll!wcslen` at `0x18007859d`
- `ntdll!wcslen` at `0x1800785a9`
- `ntdll!wcslen` at `0x18007863d`
- `ntdll!wcslen` at `0x180078648`
- `ntdll!wcslen` at `0x1800787ed`
- `ntdll!wcslen` at `0x180078806`
- `ntdll!RtlSetLastWin32Error` at `0x1800784a6`
- `ntdll!RtlSetLastWin32Error` at `0x1800784e6`
- `ntdll!RtlSetLastWin32Error` at `0x1800786aa`
- `ntdll!RtlSetLastWin32Error` at `0x1800786bd`
- `ntdll!RtlSetLastWin32Error` at `0x180078706`
- `ntdll!RtlSetLastWin32Error` at `0x180078716`
- `ntdll!RtlSetLastWin32Error` at `0x180190c0a`
- `ntdll!RtlSetLastWin32Error` at `0x180190c60`
- `ntdll!RtlSetLastWin32Error` at `0x1800784a6`
- `ntdll!RtlSetLastWin32Error` at `0x1800784e6`
- `ntdll!RtlSetLastWin32Error` at `0x1800786aa`
- `ntdll!RtlSetLastWin32Error` at `0x1800786bd`
- `ntdll!RtlSetLastWin32Error` at `0x180078706`
- `ntdll!RtlSetLastWin32Error` at `0x180078716`
- `ntdll!RtlSetLastWin32Error` at `0x180190c0a`
- `ntdll!RtlSetLastWin32Error` at `0x180190c60`
- `ntdll!RtlFreeHeap` at `0x18007805c`
- `ntdll!RtlFreeHeap` at `0x18007810f`
- `ntdll!RtlFreeHeap` at `0x18007832e`
- `ntdll!RtlFreeHeap` at `0x180078350`
- `ntdll!RtlFreeHeap` at `0x18007836d`
- `ntdll!RtlFreeHeap` at `0x1800783c7`
- `ntdll!RtlFreeHeap` at `0x180078455`
- `ntdll!RtlFreeHeap` at `0x180078522`
- `ntdll!RtlFreeHeap` at `0x180078557`
- `ntdll!RtlFreeHeap` at `0x180078684`
- `ntdll!RtlFreeHeap` at `0x1800786ed`
- `ntdll!RtlFreeHeap` at `0x18007878b`
- `ntdll!RtlFreeHeap` at `0x1800787a9`
- `ntdll!RtlFreeHeap` at `0x1800787ca`
- `ntdll!RtlFreeHeap` at `0x180190c37`
- `ntdll!RtlFreeHeap` at `0x180190c58`
- `ntdll!RtlFreeHeap` at `0x18007805c`
- `ntdll!RtlFreeHeap` at `0x18007810f`
- `ntdll!RtlFreeHeap` at `0x18007832e`
- `ntdll!RtlFreeHeap` at `0x180078350`
- `ntdll!RtlFreeHeap` at `0x18007836d`
- `ntdll!RtlFreeHeap` at `0x1800783c7`
- `ntdll!RtlFreeHeap` at `0x180078455`
- `ntdll!RtlFreeHeap` at `0x180078522`
- `ntdll!RtlFreeHeap` at `0x180078557`
- `ntdll!RtlFreeHeap` at `0x180078684`
- `ntdll!RtlFreeHeap` at `0x1800786ed`
- `ntdll!RtlFreeHeap` at `0x18007878b`
- `ntdll!RtlFreeHeap` at `0x1800787a9`
- `ntdll!RtlFreeHeap` at `0x1800787ca`
- `ntdll!RtlFreeHeap` at `0x180190c37`
- `ntdll!RtlFreeHeap` at `0x180190c58`
- `ntdll!NtQueryObject` at `0x1800780a7`
- `ntdll!NtQueryObject` at `0x1800780a7`
- `ntdll!RtlAllocateHeap` at `0x180078078`
- `ntdll!RtlAllocateHeap` at `0x18007812b`
- `ntdll!RtlAllocateHeap` at `0x1800783e3`
- `ntdll!RtlAllocateHeap` at `0x1800785d3`
- `ntdll!RtlAllocateHeap` at `0x180078078`
- `ntdll!RtlAllocateHeap` at `0x18007812b`
- `ntdll!RtlAllocateHeap` at `0x1800783e3`
- `ntdll!RtlAllocateHeap` at `0x1800785d3`

## pseudocode

```c

```
