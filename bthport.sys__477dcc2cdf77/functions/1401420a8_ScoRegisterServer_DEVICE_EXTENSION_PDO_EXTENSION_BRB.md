# ScoRegisterServer(DEVICE_EXTENSION *,PDO_EXTENSION *,_BRB *)

- ea: `0x1401420a8`
- end: `0x140142843`
- name: `?ScoRegisterServer@@YAJPEAUDEVICE_EXTENSION@@PEAUPDO_EXTENSION@@PEAU_BRB@@@Z`
- size: `1947`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, struct PDO_EXTENSION *, struct _BRB *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x14001d31c`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005b4c`
- `0x14000bdb8`
- `0x14001be50`
- `0x14002a354`
- `0x1401420a8`
- `0x140142ba4`
- `0x140161c78`
- `0x140161d7c`
- `0x140165580`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1401426d4`
- `ntoskrnl!ObfReferenceObject` at `0x1401426d4`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14014268b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14014268b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401427da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401427da`
- `ntoskrnl!ExAllocatePool2` at `0x14014242c`
- `ntoskrnl!ExAllocatePool2` at `0x14014242c`
- `ntoskrnl!KeInitializeEvent` at `0x1401424cf`
- `ntoskrnl!KeInitializeEvent` at `0x1401424cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140142569`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140142569`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401426a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401426a6`

## pseudocode

```c

```
