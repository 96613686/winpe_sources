# AfdSanCancelConnect

- ea: `0x14003f690`
- end: `0x14003f7cf`
- name: `AfdSanCancelConnect`
- size: `319`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000f390`
- `0x14003f690`
- `0x14003f7d8`
- `0x140093008`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003f740`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003f7a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003f740`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003f7a3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003f74f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003f7b2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003f74f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003f7b2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003f6c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003f6c8`
- `ntoskrnl!IofCompleteRequest` at `0x14003f789`
- `ntoskrnl!IofCompleteRequest` at `0x14003f789`

## pseudocode

```c

```
