# SMPInt_HandleSignDataBRB(DEVICE_EXTENSION *,_BRB *)

- ea: `0x1401f3440`
- end: `0x1401f377d`
- name: `?SMPInt_HandleSignDataBRB@@YAJPEAUDEVICE_EXTENSION@@PEAU_BRB@@@Z`
- size: `829`
- prototype: `int(struct DEVICE_EXTENSION *, struct _BRB *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001d31c`
- `0x1401f4dc4`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x14005fc60`
- `0x140161d7c`
- `0x1401f3440`
- `0x140208c4c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f36ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f36ea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f36de`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f36de`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f3644`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f3644`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f362e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f362e`

## pseudocode

```c

```
