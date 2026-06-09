# CJobBase::StartJob(IOperationCompletionCallback *)

- ea: `0x140005554`
- end: `0x140005881`
- name: `?StartJob@CJobBase@@QEAAHPEAVIOperationCompletionCallback@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(CJobBase *__hidden this, struct IOperationCompletionCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005430`

## callees

- `0x140005554`
- `0x1400067b0`
- `0x1400122e0`
- `0x14002aa28`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005676`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005676`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005615`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005615`

## pseudocode

```c

```
