# __imp_load_?IsRTLReading@Element@DirectUI@@UEAA_NXZ

- ea: `0x18000285c`
- end: `0x180002868`
- name: `__imp_load_?IsRTLReading@Element@DirectUI@@UEAA_NXZ`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?IsRTLReading@Element@DirectUI@@UEAA_NXZ` at `0x18000285c`

## pseudocode

```c
__int64 load__IsRTLReading_Element_DirectUI__UEAA_NXZ()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000285c  lea     rax, __imp_?IsRTLReading@Element@DirectUI@@UEAA_NXZ; DirectUI::Element::IsRTLReading(void)
0x180002863  jmp     __tailMerge_dui70_dll
```
