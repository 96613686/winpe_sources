# WskTdiTLRequestSendMessages

- ea: `0x140065b90`
- end: `0x140065f1c`
- name: `WskTdiTLRequestSendMessages`
- size: `908`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140005b60`
- `0x1400309d0`
- `0x140065b90`
- `0x140072800`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140065cb6`
- `ntoskrnl!IoFreeIrp` at `0x140065ef9`
- `ntoskrnl!IoFreeIrp` at `0x140065cb6`
- `ntoskrnl!IoFreeIrp` at `0x140065ef9`
- `ntoskrnl!IoAllocateIrp` at `0x140065bd7`
- `ntoskrnl!IoAllocateIrp` at `0x140065bd7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065c85`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065c85`
- `ntoskrnl!IoBuildPartialMdl` at `0x140065c4c`
- `ntoskrnl!IoBuildPartialMdl` at `0x140065c4c`
- `ntoskrnl!IoFreeMdl` at `0x140065ca7`
- `ntoskrnl!IoFreeMdl` at `0x140065eea`
- `ntoskrnl!IoFreeMdl` at `0x140065ca7`
- `ntoskrnl!IoFreeMdl` at `0x140065eea`
- `ntoskrnl!IoAllocateMdl` at `0x140065c21`
- `ntoskrnl!IoAllocateMdl` at `0x140065c21`
- `ntoskrnl!IofCallDriver` at `0x140065eba`
- `ntoskrnl!IofCallDriver` at `0x140065eba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065dbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065dbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065de6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065ed0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065de6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065ed0`

## pseudocode

```c

```
