# WskProIRPListen

- ea: `0x140060ab0`
- end: `0x140060c08`
- name: `WskProIRPListen`
- size: `344`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x140060ab0`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140060bed`
- `ntoskrnl!IofCompleteRequest` at `0x140060bed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060afe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060afe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060b3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060bcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060b3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060bcd`

## pseudocode

```c

```
