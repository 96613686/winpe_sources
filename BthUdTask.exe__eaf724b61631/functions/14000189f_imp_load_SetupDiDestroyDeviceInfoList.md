# __imp_load_SetupDiDestroyDeviceInfoList

- ea: `0x14000189f`
- end: `0x1400018ab`
- name: `__imp_load_SetupDiDestroyDeviceInfoList`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x140001820`

## import_xrefs

- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x14000189f`

## pseudocode

```c
__int64 load_SetupDiDestroyDeviceInfoList()
{
  return _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000189f  lea     rax, __imp_SetupDiDestroyDeviceInfoList
0x1400018a6  jmp     __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_0_dll
```
