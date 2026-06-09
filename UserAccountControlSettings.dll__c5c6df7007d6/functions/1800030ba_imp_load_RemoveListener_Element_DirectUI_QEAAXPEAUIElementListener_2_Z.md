# __imp_load_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z

- ea: `0x1800030ba`
- end: `0x1800030c6`
- name: `__imp_load_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x1800030ba`

## pseudocode

```c
__int64 load__RemoveListener_Element_DirectUI__QEAAXPEAUIElementListener_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x1800030ba  lea     rax, __imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x1800030c1  jmp     __tailMerge_dui70_dll
```
