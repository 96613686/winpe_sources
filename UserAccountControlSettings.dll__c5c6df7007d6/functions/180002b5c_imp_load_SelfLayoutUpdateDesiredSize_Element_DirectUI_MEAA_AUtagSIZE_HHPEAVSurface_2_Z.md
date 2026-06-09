# __imp_load_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z

- ea: `0x180002b5c`
- end: `0x180002b68`
- name: `__imp_load_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180002b5c`

## pseudocode

```c
__int64 load___SelfLayoutUpdateDesiredSize_Element_DirectUI__MEAA_AUtagSIZE__HHPEAVSurface_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002b5c  lea     rax, __imp_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)
0x180002b63  jmp     __tailMerge_dui70_dll
```
