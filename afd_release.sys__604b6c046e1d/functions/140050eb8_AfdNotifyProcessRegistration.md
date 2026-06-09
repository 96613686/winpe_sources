# AfdNotifyProcessRegistration

- ea: `0x140050eb8`
- end: `0x1400511b9`
- name: `AfdNotifyProcessRegistration`
- size: `769`
- prototype: `__int64 __fastcall(KPROCESSOR_MODE, void *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400511c0`

## callees

- `0x140018190`
- `0x140050b88`
- `0x140050be4`
- `0x140050eb8`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140050f7a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140050f7a`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x140051062`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x140051062`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14005115a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14005115a`
- `ntoskrnl!ObfReferenceObject` at `0x140050f5b`
- `ntoskrnl!ObfReferenceObject` at `0x140051081`
- `ntoskrnl!ObfReferenceObject` at `0x140050f5b`
- `ntoskrnl!ObfReferenceObject` at `0x140051081`
- `ntoskrnl!ObfDereferenceObject` at `0x140051192`
- `ntoskrnl!ObfDereferenceObject` at `0x140051192`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050fb8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051149`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050fb8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051149`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050f97`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005109a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050f97`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005109a`
- `ntoskrnl!IoFileObjectType` at `0x140050ff9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005101f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005101f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005117e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005117e`
- `ntoskrnl!ExAllocatePool2` at `0x140050fd0`
- `ntoskrnl!ExAllocatePool2` at `0x140050fd0`

## pseudocode

```c

```
