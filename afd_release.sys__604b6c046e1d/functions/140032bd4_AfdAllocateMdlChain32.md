# AfdAllocateMdlChain32

- ea: `0x140032bd4`
- end: `0x140032d7b`
- name: `AfdAllocateMdlChain32`
- size: `423`
- prototype: `__int64 __fastcall(__int64, ULONG *, unsigned int, LOCK_OPERATION, _DWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140007350`
- `0x1400086d0`
- `0x14001f120`
- `0x140022470`
- `0x140054228`

## callees

- `0x14002fd5c`
- `0x140032bd4`
- `0x14009214c`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140032cf0`
- `ntoskrnl!ExRaiseStatus` at `0x140032cf0`
- `ntoskrnl!ProbeForRead` at `0x140032d16`
- `ntoskrnl!ProbeForRead` at `0x140032d16`
- `ntoskrnl!IoFreeMdl` at `0x140032d4c`
- `ntoskrnl!IoFreeMdl` at `0x140032d4c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140032c9c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140032c9c`
- `ntoskrnl!IoAllocateMdl` at `0x140032c71`
- `ntoskrnl!IoAllocateMdl` at `0x140032c71`

## pseudocode

```c

```
