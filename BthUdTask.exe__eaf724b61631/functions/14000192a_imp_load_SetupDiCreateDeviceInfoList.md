# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x14000192a`
- end: `0x140001936`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400018ab`

## import_xrefs

- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x14000192a`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll();
}

```

## disassembly

```asm
0x14000192a  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x140001931  jmp     __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll
```
