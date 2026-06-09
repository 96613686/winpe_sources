# SetCommState

- ea: `0x18017e880`
- end: `0x18017ecba`
- name: `SetCommState`
- size: `1082`
- prototype: `BOOL __stdcall(HANDLE hFile, LPDCB lpDCB)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18017e790`
- `0x18017e880`

## callees

- `0x1800134a0`
- `0x1800138c0`
- `0x180048f30`
- `0x180107750`
- `0x180110590`
- `0x18017e880`
- `0x180188f10`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18017e964`
- `ntdll!NtWaitForSingleObject` at `0x18017eb97`
- `ntdll!NtWaitForSingleObject` at `0x18017ec1c`
- `ntdll!NtWaitForSingleObject` at `0x18017ec8c`
- `ntdll!NtWaitForSingleObject` at `0x18017e964`
- `ntdll!NtWaitForSingleObject` at `0x18017eb97`
- `ntdll!NtWaitForSingleObject` at `0x18017ec1c`
- `ntdll!NtWaitForSingleObject` at `0x18017ec8c`
- `ntdll!NtDeviceIoControlFile` at `0x18017e94d`
- `ntdll!NtDeviceIoControlFile` at `0x18017eb7c`
- `ntdll!NtDeviceIoControlFile` at `0x18017ec07`
- `ntdll!NtDeviceIoControlFile` at `0x18017ec77`
- `ntdll!NtDeviceIoControlFile` at `0x18017e94d`
- `ntdll!NtDeviceIoControlFile` at `0x18017eb7c`
- `ntdll!NtDeviceIoControlFile` at `0x18017ec07`
- `ntdll!NtDeviceIoControlFile` at `0x18017ec77`

## pseudocode

```c

```
