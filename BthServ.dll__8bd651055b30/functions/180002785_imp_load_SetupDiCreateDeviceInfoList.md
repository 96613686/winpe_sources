# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x180002785`
- end: `0x180002791`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002706`

## import_xrefs

- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x180002785`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll();
}

```

## disassembly

```asm
0x180002785  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x18000278c  jmp     __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll
```
