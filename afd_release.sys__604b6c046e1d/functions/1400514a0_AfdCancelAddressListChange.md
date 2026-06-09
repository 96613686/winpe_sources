# AfdCancelAddressListChange

- ea: `0x1400514a0`
- end: `0x140051698`
- name: `AfdCancelAddressListChange`
- size: `504`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400514a0`
- `0x140093008`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400514c6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400514c6`
- `ntoskrnl!IofCompleteRequest` at `0x14005164c`
- `ntoskrnl!IofCompleteRequest` at `0x14005164c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005156c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005156c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400515bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400515ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400515bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400515ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051554`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051604`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051617`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051554`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051604`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140051617`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140051516`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005158a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140051516`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005158a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005162b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005162b`

## pseudocode

```c

```
