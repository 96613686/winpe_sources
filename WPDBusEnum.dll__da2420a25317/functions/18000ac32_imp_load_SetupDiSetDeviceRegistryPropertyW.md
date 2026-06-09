# __imp_load_SetupDiSetDeviceRegistryPropertyW

- ea: `0x18000ac32`
- end: `0x18000ac3e`
- name: `__imp_load_SetupDiSetDeviceRegistryPropertyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceRegistryPropertyW` at `0x18000ac32`

## pseudocode

```c
__int64 load_SetupDiSetDeviceRegistryPropertyW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000ac32  lea     rax, __imp_SetupDiSetDeviceRegistryPropertyW
0x18000ac39  jmp     __tailMerge_setupapi_dll
```
