# __imp_load_?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z

- ea: `0x180002bbc`
- end: `0x180002bc8`
- name: `__imp_load_?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z` at `0x180002bbc`

## pseudocode

```c
__int64 load__UpdateTooltip_Element_DirectUI__MEAAXPEAV12__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002bbc  lea     rax, __imp_?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z; DirectUI::Element::UpdateTooltip(DirectUI::Element *)
0x180002bc3  jmp     __tailMerge_dui70_dll
```
