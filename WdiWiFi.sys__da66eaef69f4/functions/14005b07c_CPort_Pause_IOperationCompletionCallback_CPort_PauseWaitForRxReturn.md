# CPort::Pause(IOperationCompletionCallback *,CPort::PauseWaitForRxReturn)

- ea: `0x14005b07c`
- end: `0x14005b2f3`
- name: `?Pause@CPort@@QEAAHPEAVIOperationCompletionCallback@@W4PauseWaitForRxReturn@1@@Z`
- size: `631`
- prototype: `__int64 __fastcall(CPort *__hidden this, struct IOperationCompletionCallback *, enum CPort::PauseWaitForRxReturn)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002cdf0`
- `0x14005b040`
- `0x140078e30`

## callees

- `0x14002ed64`
- `0x140030bb0`
- `0x140034e04`
- `0x140034ec4`
- `0x14005b07c`
- `0x14005b2fc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14005b13a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b181`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b13a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b181`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005b0bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005b1a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005b0bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005b1a4`

## pseudocode

```c

```
