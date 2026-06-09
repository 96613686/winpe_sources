# __imp_load_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z

- ea: `0x180002a1c`
- end: `0x180002a28`
- name: `__imp_load_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z` at `0x180002a1c`

## pseudocode

```c
__int64 load__Remove_Element_DirectUI__UEAAJPEAPEAV12_I_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002a1c  lea     rax, __imp_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z; DirectUI::Element::Remove(DirectUI::Element * *,uint)
0x180002a23  jmp     __tailMerge_dui70_dll
```
