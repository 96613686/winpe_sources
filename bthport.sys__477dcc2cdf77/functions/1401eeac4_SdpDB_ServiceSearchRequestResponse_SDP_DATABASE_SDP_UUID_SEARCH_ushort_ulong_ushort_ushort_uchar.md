# SdpDB_ServiceSearchRequestResponse(_SDP_DATABASE *,_SDP_UUID_SEARCH *,ushort,ulong * *,ushort *,ushort *,uchar)

- ea: `0x1401eeac4`
- end: `0x1401eee01`
- name: `?SdpDB_ServiceSearchRequestResponse@@YAJPEAU_SDP_DATABASE@@PEAU_SDP_UUID_SEARCH@@GPEAPEAKPEAG3E@Z`
- size: `829`
- prototype: `__int64 __fastcall(struct _SDP_DATABASE *, struct _SDP_UUID_SEARCH *, unsigned __int16, unsigned int **, unsigned __int16 *, unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1401eee08`
- `0x1401eeed0`

## callees

- `0x140005608`
- `0x140005690`
- `0x1401eeac4`
- `0x1401ef1f8`
- `0x14020aa5c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1401eeb7a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401eeb7a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401eecd7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401eecd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eedd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eedd1`
- `ntoskrnl!ExAllocatePool2` at `0x1401eec21`
- `ntoskrnl!ExAllocatePool2` at `0x1401eed06`
- `ntoskrnl!ExAllocatePool2` at `0x1401eec21`
- `ntoskrnl!ExAllocatePool2` at `0x1401eed06`

## pseudocode

```c

```
