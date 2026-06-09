# AfdAllocateMdlChain

- ea: `0x140008064`
- end: `0x140008203`
- name: `AfdAllocateMdlChain`
- size: `415`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int, LOCK_OPERATION, _DWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140007350`
- `0x1400086d0`
- `0x14001f120`
- `0x140022470`
- `0x140054228`

## callees

- `0x140008064`
- `0x14002fd5c`
- `0x140092110`
- `0x14009214c`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400081ad`
- `ntoskrnl!ExRaiseStatus` at `0x1400081ad`
- `ntoskrnl!ProbeForRead` at `0x1400080c9`
- `ntoskrnl!ProbeForRead` at `0x1400080c9`
- `ntoskrnl!IoFreeMdl` at `0x1400081d4`
- `ntoskrnl!IoFreeMdl` at `0x1400081d4`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000815e`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000815e`
- `ntoskrnl!IoAllocateMdl` at `0x14000812d`
- `ntoskrnl!IoAllocateMdl` at `0x14000812d`

## pseudocode

```c

```
