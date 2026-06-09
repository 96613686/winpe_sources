# FltpRemoveVolumeContextsForFilter

- ea: `0x180056d30`
- end: `0x180056f2f`
- name: `FltpRemoveVolumeContextsForFilter`
- size: `511`
- prototype: `__int64 __fastcall(PFLT_FILTER Filter)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004d410`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x1800123e0`
- `0x180024c00`
- `0x180056d30`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180056d5a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180056d5a`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180056d88`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180056e23`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180056edc`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180056d88`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180056e23`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180056edc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180056d6a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180056e0c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180056ec5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180056d6a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180056e0c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180056ec5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180056df2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180056eab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180056f10`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180056df2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180056eab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180056f10`
- `ntoskrnl!ExReleaseFastResource` at `0x180056de6`
- `ntoskrnl!ExReleaseFastResource` at `0x180056e9f`
- `ntoskrnl!ExReleaseFastResource` at `0x180056f04`
- `ntoskrnl!ExReleaseFastResource` at `0x180056de6`
- `ntoskrnl!ExReleaseFastResource` at `0x180056e9f`
- `ntoskrnl!ExReleaseFastResource` at `0x180056f04`

## pseudocode

```c

```
