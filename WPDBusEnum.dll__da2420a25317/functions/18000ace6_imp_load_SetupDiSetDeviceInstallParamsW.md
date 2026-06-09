# __imp_load_SetupDiSetDeviceInstallParamsW

- ea: `0x18000ace6`
- end: `0x18000acf2`
- name: `__imp_load_SetupDiSetDeviceInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18000ace6`

## pseudocode

```c
__int64 load_SetupDiSetDeviceInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000ace6  lea     rax, __imp_SetupDiSetDeviceInstallParamsW
0x18000aced  jmp     __tailMerge_setupapi_dll
```
