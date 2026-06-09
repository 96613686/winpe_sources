# GetCommState

- ea: `0x180107750`
- end: `0x180107980`
- name: `GetCommState`
- size: `560`
- prototype: `BOOL __stdcall(HANDLE hFile, LPDCB lpDCB)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18017df40`
- `0x18017e880`

## callees

- `0x1800134a0`
- `0x1800138c0`
- `0x180048f30`
- `0x180107750`
- `0x180188f10`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180107937`
- `ntdll!NtWaitForSingleObject` at `0x180107952`
- `ntdll!NtWaitForSingleObject` at `0x18010796d`
- `ntdll!NtWaitForSingleObject` at `0x180196141`
- `ntdll!NtWaitForSingleObject` at `0x180107937`
- `ntdll!NtWaitForSingleObject` at `0x180107952`
- `ntdll!NtWaitForSingleObject` at `0x18010796d`
- `ntdll!NtWaitForSingleObject` at `0x180196141`
- `ntdll!NtDeviceIoControlFile` at `0x18010780e`
- `ntdll!NtDeviceIoControlFile` at `0x180107877`
- `ntdll!NtDeviceIoControlFile` at `0x1801078dc`
- `ntdll!NtDeviceIoControlFile` at `0x18019612c`
- `ntdll!NtDeviceIoControlFile` at `0x18010780e`
- `ntdll!NtDeviceIoControlFile` at `0x180107877`
- `ntdll!NtDeviceIoControlFile` at `0x1801078dc`
- `ntdll!NtDeviceIoControlFile` at `0x18019612c`

## pseudocode

```c

```
