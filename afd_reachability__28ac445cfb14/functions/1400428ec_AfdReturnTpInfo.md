# AfdReturnTpInfo

- ea: `0x1400428ec`
- end: `0x140042a6b`
- name: `AfdReturnTpInfo`
- size: `383`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003fc3c`
- `0x140042250`
- `0x140057060`
- `0x140057940`

## callees

- `0x1400428ec`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140042937`
- `ntoskrnl!IoFreeIrp` at `0x14004296b`
- `ntoskrnl!IoFreeIrp` at `0x140042937`
- `ntoskrnl!IoFreeIrp` at `0x14004296b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042a3d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042a3d`
- `ntoskrnl!IoFreeMdl` at `0x1400429d9`
- `ntoskrnl!IoFreeMdl` at `0x1400429d9`
- `ntoskrnl!MmUnlockPages` at `0x1400429c8`
- `ntoskrnl!MmUnlockPages` at `0x1400429c8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400429a6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400429a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042924`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042924`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a53`

## pseudocode

```c

```
