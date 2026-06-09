# WskProIRPReceiveFrom

- ea: `0x140060c10`
- end: `0x140060d69`
- name: `WskProIRPReceiveFrom`
- size: `345`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x140060c10`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140060cec`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140060cec`
- `ntoskrnl!IofCompleteRequest` at `0x140060d05`
- `ntoskrnl!IofCompleteRequest` at `0x140060d05`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060cdc`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060cdc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060c85`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060c85`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060cb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060d47`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060cb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060d47`

## pseudocode

```c

```
