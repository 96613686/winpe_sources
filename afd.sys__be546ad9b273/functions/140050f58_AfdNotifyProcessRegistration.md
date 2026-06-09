# AfdNotifyProcessRegistration

- ea: `0x140050f58`
- end: `0x140051259`
- name: `AfdNotifyProcessRegistration`
- size: `769`
- prototype: `__int64 __fastcall(KPROCESSOR_MODE, void *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140051260`

## callees

- `0x140018190`
- `0x140050c28`
- `0x140050c84`
- `0x140050f58`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14005101a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005101a`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x140051102`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x140051102`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400511fa`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400511fa`
- `ntoskrnl!ObfReferenceObject` at `0x140050ffb`
- `ntoskrnl!ObfReferenceObject` at `0x140051121`
- `ntoskrnl!ObfReferenceObject` at `0x140050ffb`
- `ntoskrnl!ObfReferenceObject` at `0x140051121`
- `ntoskrnl!ObfDereferenceObject` at `0x140051232`
- `ntoskrnl!ObfDereferenceObject` at `0x140051232`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051058`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400511e9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051058`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400511e9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140051037`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005113a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140051037`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005113a`
- `ntoskrnl!IoFileObjectType` at `0x140051099`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400510bf`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400510bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005121e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005121e`
- `ntoskrnl!ExAllocatePool2` at `0x140051070`
- `ntoskrnl!ExAllocatePool2` at `0x140051070`

## pseudocode

```c

```
