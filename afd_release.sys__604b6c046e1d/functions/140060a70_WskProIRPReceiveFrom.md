# WskProIRPReceiveFrom

- ea: `0x140060a70`
- end: `0x140060bc9`
- name: `WskProIRPReceiveFrom`
- size: `345`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140060a70`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140060b4c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140060b4c`
- `ntoskrnl!IofCompleteRequest` at `0x140060b65`
- `ntoskrnl!IofCompleteRequest` at `0x140060b65`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060b3c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060b3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060ae5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060ae5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060b17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060ba7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060b17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060ba7`

## pseudocode

```c

```
