# AfdTimeoutPoll

- ea: `0x140025d80`
- end: `0x140026061`
- name: `AfdTimeoutPoll`
- size: `737`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140018680`
- `0x140018b20`
- `0x140025d80`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140025ed5`
- `ntoskrnl!KeCancelTimer` at `0x140025ed5`
- `ntoskrnl!KeInsertQueueApc` at `0x140025fbd`
- `ntoskrnl!KeInsertQueueApc` at `0x140025fbd`
- `ntoskrnl!KeInitializeApc` at `0x140025f9f`
- `ntoskrnl!KeInitializeApc` at `0x140025f9f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140025f13`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140025f13`
- `ntoskrnl!IofCompleteRequest` at `0x140025eb0`
- `ntoskrnl!IofCompleteRequest` at `0x140025eb0`
- `ntoskrnl!ObfDereferenceObject` at `0x140025e40`
- `ntoskrnl!ObfDereferenceObject` at `0x140025f2b`
- `ntoskrnl!ObfDereferenceObject` at `0x140025fd5`
- `ntoskrnl!ObfDereferenceObject` at `0x14002602d`
- `ntoskrnl!ObfDereferenceObject` at `0x140025e40`
- `ntoskrnl!ObfDereferenceObject` at `0x140025f2b`
- `ntoskrnl!ObfDereferenceObject` at `0x140025fd5`
- `ntoskrnl!ObfDereferenceObject` at `0x14002602d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140025f02`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140025f02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e9a`

## pseudocode

```c

```
