# DriverEntry

- ea: `0x180011d54`
- end: `0x180011d5a`
- name: `DriverEntry`
- size: `6`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001f010`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  return -1073741822;
}

```

## disassembly

```asm
0x180011d54  mov     eax, 0C0000002h
0x180011d59  retn
```
