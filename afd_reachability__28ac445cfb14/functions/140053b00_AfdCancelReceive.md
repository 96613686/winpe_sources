# AfdCancelReceive

- ea: `0x140053b00`
- end: `0x140053be1`
- name: `AfdCancelReceive`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140053b00`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140053b75`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140053b75`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140053b84`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140053b84`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140053b38`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140053b38`
- `ntoskrnl!IofCompleteRequest` at `0x140053bc4`
- `ntoskrnl!IofCompleteRequest` at `0x140053bc4`

## pseudocode

```c

```
