# WskProIRPBind

- ea: `0x140003b90`
- end: `0x140003d16`
- name: `WskProIRPBind`
- size: `390`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140003b90`
- `0x140005b60`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003cfc`
- `ntoskrnl!IofCompleteRequest` at `0x140003cfc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c25`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c25`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003cdc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003cdc`

## pseudocode

```c

```
