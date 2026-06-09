# WskProIRPAccept

- ea: `0x140060800`
- end: `0x1400609c5`
- name: `WskProIRPAccept`
- size: `453`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x140060800`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140060941`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140060941`
- `ntoskrnl!IofCompleteRequest` at `0x1400609a6`
- `ntoskrnl!IofCompleteRequest` at `0x1400609a6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060931`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140060931`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400608da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400608da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006090c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060986`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006090c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060986`

## pseudocode

```c

```
