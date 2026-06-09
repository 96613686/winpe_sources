# WskTdiCOMPReceive

- ea: `0x140033f00`
- end: `0x1400340a1`
- name: `WskTdiCOMPReceive`
- size: `417`
- prototype: `__int64 __fastcall(__int64, IRP *, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140015ea0`
- `0x140033f00`
- `0x14004efd0`
- `0x140063fc0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140034086`
- `ntoskrnl!IoFreeIrp` at `0x140034086`
- `ntoskrnl!IoAllocateIrp` at `0x140033f85`
- `ntoskrnl!IoAllocateIrp` at `0x140033f85`
- `ntoskrnl!IoFreeMdl` at `0x140033f32`
- `ntoskrnl!IoFreeMdl` at `0x140033f32`
- `ntoskrnl!IofCallDriver` at `0x140034077`
- `ntoskrnl!IofCallDriver` at `0x140034077`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033fa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033fa7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033fec`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033fec`

## pseudocode

```c

```
