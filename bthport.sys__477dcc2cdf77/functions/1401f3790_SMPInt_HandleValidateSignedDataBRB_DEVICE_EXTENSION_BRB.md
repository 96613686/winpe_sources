# SMPInt_HandleValidateSignedDataBRB(DEVICE_EXTENSION *,_BRB *)

- ea: `0x1401f3790`
- end: `0x1401f3b56`
- name: `?SMPInt_HandleValidateSignedDataBRB@@YAJPEAUDEVICE_EXTENSION@@PEAU_BRB@@@Z`
- size: `966`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, struct _BRB *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001d31c`
- `0x1401f4f5c`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x14005fc60`
- `0x140161d7c`
- `0x1401f3790`
- `0x140208c4c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f3abf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f3abf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f3ab3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f3ab3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f3996`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f3996`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f3980`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f3980`

## pseudocode

```c

```
