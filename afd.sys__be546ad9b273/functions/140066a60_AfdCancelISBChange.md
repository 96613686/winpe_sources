# AfdCancelISBChange

- ea: `0x140066a60`
- end: `0x140066b3b`
- name: `AfdCancelISBChange`
- size: `219`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140066a60`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140066ab1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140066af3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140066ab1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140066af3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140066ac0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140066b02`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140066ac0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140066b02`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140066a98`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140066a98`
- `ntoskrnl!IofCompleteRequest` at `0x140066b26`
- `ntoskrnl!IofCompleteRequest` at `0x140066b26`

## pseudocode

```c

```
