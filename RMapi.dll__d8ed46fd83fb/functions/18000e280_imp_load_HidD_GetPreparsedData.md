# __imp_load_HidD_GetPreparsedData

- ea: `0x18000e280`
- end: `0x18000e28c`
- name: `__imp_load_HidD_GetPreparsedData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000e11c`

## import_xrefs

- `HID!HidD_GetPreparsedData` at `0x18000e280`

## pseudocode

```c
__int64 load_HidD_GetPreparsedData()
{
  return _tailMerge_hid_dll();
}

```

## disassembly

```asm
0x18000e280  lea     rax, __imp_HidD_GetPreparsedData
0x18000e287  jmp     __tailMerge_hid_dll
```
