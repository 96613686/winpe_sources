# __imp_load_OleCreatePictureIndirectExt

- ea: `0x18004eae7`
- end: `0x18004eaf3`
- name: `__imp_load_OleCreatePictureIndirectExt`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004e8ca`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!OleCreatePictureIndirectExt` at `0x18004eae7`

## pseudocode

```c
__int64 load_OleCreatePictureIndirectExt()
{
  return _tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004eae7  lea     rax, __imp_OleCreatePictureIndirectExt
0x18004eaee  jmp     __tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll
```
