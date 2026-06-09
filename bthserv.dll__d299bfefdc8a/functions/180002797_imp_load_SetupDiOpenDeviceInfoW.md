# __imp_load_SetupDiOpenDeviceInfoW

- ea: `0x180002797`
- end: `0x1800027a3`
- name: `__imp_load_SetupDiOpenDeviceInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002706`

## import_xrefs

- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x180002797`

## pseudocode

```c
__int64 load_SetupDiOpenDeviceInfoW()
{
  return _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll();
}

```

## disassembly

```asm
0x180002797  lea     rax, __imp_SetupDiOpenDeviceInfoW
0x18000279e  jmp     __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll
```
