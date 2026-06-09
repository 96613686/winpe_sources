# SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)

- ea: `0x140087950`
- end: `0x140087a61`
- name: `?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z`
- size: `273`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD dwIoControlCode@<edx>, struct _OVERLAPPED *@<r8>, void *@<r9>, DWORD nInBufferSize, void *, unsigned int, unsigned int *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400858f0`
- `0x140085d64`
- `0x140085df4`
- `0x140086f3c`
- `0x1401b6d28`
- `0x1401b6edc`
- `0x1401b7398`
- `0x1401b9d30`

## callees

- `0x140087950`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14008799b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14008799b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087a05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087a3a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400879f3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400879f3`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140087a29`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140087a29`

## pseudocode

```c

```
