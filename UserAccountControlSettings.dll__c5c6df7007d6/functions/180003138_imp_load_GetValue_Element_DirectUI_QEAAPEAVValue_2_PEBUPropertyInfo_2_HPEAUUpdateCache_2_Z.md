# __imp_load_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z

- ea: `0x180003138`
- end: `0x180003144`
- name: `__imp_load_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180003138`

## pseudocode

```c
__int64 load__GetValue_Element_DirectUI__QEAAPEAVValue_2_PEBUPropertyInfo_2_HPEAUUpdateCache_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003138  lea     rax, __imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000313f  jmp     __tailMerge_dui70_dll
```
