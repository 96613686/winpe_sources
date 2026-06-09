# WskProIRPListen

- ea: `0x140060910`
- end: `0x140060a68`
- name: `WskProIRPListen`
- size: `344`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140060910`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140060a4d`
- `ntoskrnl!IofCompleteRequest` at `0x140060a4d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006095e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006095e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006099c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060a2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006099c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060a2d`

## pseudocode

```c

```
