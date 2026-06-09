# __imp_load_HidD_FreePreparsedData

- ea: `0x18000e26e`
- end: `0x18000e27a`
- name: `__imp_load_HidD_FreePreparsedData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000e11c`

## import_xrefs

- `HID!HidD_FreePreparsedData` at `0x18000e26e`

## pseudocode

```c
__int64 load_HidD_FreePreparsedData()
{
  return _tailMerge_hid_dll();
}

```

## disassembly

```asm
0x18000e26e  lea     rax, __imp_HidD_FreePreparsedData
0x18000e275  jmp     __tailMerge_hid_dll
```
