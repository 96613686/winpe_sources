# DriverEntry

- ea: `0x140079f58`
- end: `0x14007a1a8`
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
- `0x140056a50`
- `0x140056afc`
- `0x140079e54`
- `0x140079f58`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x1400a9078`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007a097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a140`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a140`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140079fc0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140079fc0`
- `FLTMGR!FltStartFiltering` at `0x14007a0c0`
- `FLTMGR!FltStartFiltering` at `0x14007a0c0`

## pseudocode

```c

```
