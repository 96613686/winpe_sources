# AfdSanFindSwitchSocketByProcessContext

- ea: `0x14005d420`
- end: `0x14005d5b9`
- name: `AfdSanFindSwitchSocketByProcessContext`
- size: `409`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003f97c`

## callees

- `0x140019190`
- `0x1400191f0`
- `0x14005d420`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005d44d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005d44d`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d58a`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d58a`
- `ntoskrnl!ObFindHandleForObject` at `0x14005d55d`
- `ntoskrnl!ObFindHandleForObject` at `0x14005d55d`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005d51e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005d51e`
- `ntoskrnl!ObfReferenceObject` at `0x14005d4cc`
- `ntoskrnl!ObfReferenceObject` at `0x14005d4cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d4e2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d4e2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d4b0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d4b0`
- `ntoskrnl!IoFileObjectType` at `0x14005d53d`

## pseudocode

```c

```
