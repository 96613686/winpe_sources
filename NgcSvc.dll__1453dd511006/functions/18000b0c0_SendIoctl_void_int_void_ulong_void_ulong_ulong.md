# SendIoctl(void *,int,void *,ulong,void *,ulong,ulong *)

- ea: `0x18000b0c0`
- end: `0x18000b307`
- name: `?SendIoctl@@YAJPEAXH0K0KPEAK@Z`
- size: `583`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000aaf8`
- `0x18000adcc`
- `0x1800379cc`
- `0x18003826c`
- `0x180050f6c`

## callees

- `0x18000782c`
- `0x180007964`
- `0x18000948c`
- `0x18000b0c0`
- `0x180048304`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b12f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b12f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b1ef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1b5`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18000b249`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18000b249`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b1ab`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b1ab`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b208`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b286`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b208`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b286`

## pseudocode

```c

```
