# AfdCancelWaitForListen

- ea: `0x140004ab0`
- end: `0x140004c06`
- name: `AfdCancelWaitForListen`
- size: `342`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400049b0`
- `0x140004ab0`
- `0x140004c10`
- `0x140093008`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004b64`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004be9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004b64`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004be9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004b73`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004bf8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004b73`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004bf8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140004af6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140004af6`
- `ntoskrnl!IofCompleteRequest` at `0x140004b88`
- `ntoskrnl!IofCompleteRequest` at `0x140004b88`

## pseudocode

```c

```
