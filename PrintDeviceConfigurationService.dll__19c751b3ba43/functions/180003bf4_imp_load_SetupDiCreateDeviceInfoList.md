# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x180003bf4`
- end: `0x180003c00`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180003b75`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180003bf4`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180003bf4  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x180003bfb  jmp     __tailMerge_setupapi_dll
```
