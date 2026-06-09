# __imp_load_SetupDiGetDeviceInstallParamsW

- ea: `0x18000acd4`
- end: `0x18000ace0`
- name: `__imp_load_SetupDiGetDeviceInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18000acd4`

## pseudocode

```c
__int64 load_SetupDiGetDeviceInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000acd4  lea     rax, __imp_SetupDiGetDeviceInstallParamsW
0x18000acdb  jmp     __tailMerge_setupapi_dll
```
