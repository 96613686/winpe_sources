# WskProIRPAccept

- ea: `0x140060660`
- end: `0x140060825`
- name: `WskProIRPAccept`
- size: `453`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140060660`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400607a1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400607a1`
- `ntoskrnl!IofCompleteRequest` at `0x140060806`
- `ntoskrnl!IofCompleteRequest` at `0x140060806`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060791`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060791`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006073a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006073a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006076c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400607e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006076c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400607e6`

## pseudocode

```c

```
