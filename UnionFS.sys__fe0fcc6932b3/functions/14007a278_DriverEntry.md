# DriverEntry

- ea: `0x14007a278`
- end: `0x14007a4c8`
- name: `DriverEntry`
- size: `592`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400a9010`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140006390`
- `0x14000701c`
- `0x140056bd0`
- `0x140056c7c`
- `0x14007a174`
- `0x14007a278`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x1400a9078`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007a3b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a460`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a3b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a460`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14007a2e0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14007a2e0`
- `FLTMGR!FltStartFiltering` at `0x14007a3e0`
- `FLTMGR!FltStartFiltering` at `0x14007a3e0`

## pseudocode

```c

```
