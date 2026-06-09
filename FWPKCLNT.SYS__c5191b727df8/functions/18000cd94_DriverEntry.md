# DriverEntry

- ea: `0x18000cd94`
- end: `0x18000ce32`
- name: `DriverEntry`
- size: `158`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006c010`

## callees

- `0x18000cd94`
- `0x18000d98c`
- `0x18000da98`
- `0x1800203c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000ce11`
- `ntoskrnl!ZwClose` at `0x18000ce11`

## pseudocode

```c

```
