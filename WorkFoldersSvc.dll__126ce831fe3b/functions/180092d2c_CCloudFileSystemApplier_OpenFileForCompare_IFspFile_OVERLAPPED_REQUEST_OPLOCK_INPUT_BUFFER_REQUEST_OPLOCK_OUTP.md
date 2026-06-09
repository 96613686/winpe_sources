# CCloudFileSystemApplier::OpenFileForCompare(IFspFile *,_OVERLAPPED *,_REQUEST_OPLOCK_INPUT_BUFFER *,_REQUEST_OPLOCK_OUTPUT_BUFFER *,void * *)

- ea: `0x180092d2c`
- end: `0x180093353`
- name: `?OpenFileForCompare@CCloudFileSystemApplier@@AEAAJPEAUIFspFile@@PEAU_OVERLAPPED@@PEAU_REQUEST_OPLOCK_INPUT_BUFFER@@PEAU_REQUEST_OPLOCK_OUTPUT_BUFFER@@PEAPEAX@Z`
- size: `1575`
- prototype: `int(CCloudFileSystemApplier *__hidden this, struct IFspFile *, struct _OVERLAPPED *, struct _REQUEST_OPLOCK_INPUT_BUFFER *, struct _REQUEST_OPLOCK_OUTPUT_BUFFER *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008db80`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x180058d88`
- `0x18008c1d4`
- `0x18008c218`
- `0x180092d2c`
- `0x1800963d0`
- `0x180098eec`
- `0x1800bb748`
- `0x18013e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180093160`
- `KERNEL32!DeviceIoControl` at `0x180093160`
- `KERNEL32!CancelIo` at `0x1800932de`
- `KERNEL32!CancelIo` at `0x1800932de`
- `KERNEL32!WaitForSingleObject` at `0x1800932f9`
- `KERNEL32!WaitForSingleObject` at `0x1800932f9`
- `KERNEL32!GetLastError` at `0x18009317b`
- `KERNEL32!GetLastError` at `0x18009317b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009310a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009310a`
- `ntdll!NtClose` at `0x1800932b3`
- `ntdll!NtClose` at `0x1800932e7`
- `ntdll!NtClose` at `0x1800932b3`
- `ntdll!NtClose` at `0x1800932e7`

## string_xrefs

- `0x180092db9`: `CCloudFileSystemApplier::OpenFileForCompare`

## pseudocode

```c

```
