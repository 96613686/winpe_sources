# AfdSanFindSwitchSocketByProcessContext

- ea: `0x14005d5c0`
- end: `0x14005d759`
- name: `AfdSanFindSwitchSocketByProcessContext`
- size: `409`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003f99c`

## callees

- `0x140019190`
- `0x1400191f0`
- `0x14005d5c0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005d5ed`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005d5ed`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d72a`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d72a`
- `ntoskrnl!ObFindHandleForObject` at `0x14005d6fd`
- `ntoskrnl!ObFindHandleForObject` at `0x14005d6fd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005d6be`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005d6be`
- `ntoskrnl!ObfReferenceObject` at `0x14005d66c`
- `ntoskrnl!ObfReferenceObject` at `0x14005d66c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d682`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d682`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d650`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d650`
- `ntoskrnl!IoFileObjectType` at `0x14005d6dd`

## pseudocode

```c

```
