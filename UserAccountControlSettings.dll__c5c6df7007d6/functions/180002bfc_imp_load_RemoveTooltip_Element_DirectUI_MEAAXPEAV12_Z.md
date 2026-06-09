# __imp_load_?RemoveTooltip@Element@DirectUI@@MEAAXPEAV12@@Z

- ea: `0x180002bfc`
- end: `0x180002c08`
- name: `__imp_load_?RemoveTooltip@Element@DirectUI@@MEAAXPEAV12@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?RemoveTooltip@Element@DirectUI@@MEAAXPEAV12@@Z` at `0x180002bfc`

## pseudocode

```c
__int64 load__RemoveTooltip_Element_DirectUI__MEAAXPEAV12__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002bfc  lea     rax, __imp_?RemoveTooltip@Element@DirectUI@@MEAAXPEAV12@@Z; DirectUI::Element::RemoveTooltip(DirectUI::Element *)
0x180002c03  jmp     __tailMerge_dui70_dll
```
