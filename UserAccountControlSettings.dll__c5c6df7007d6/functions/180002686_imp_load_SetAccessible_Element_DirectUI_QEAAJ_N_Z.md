# __imp_load_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z

- ea: `0x180002686`
- end: `0x180002692`
- name: `__imp_load_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180002686`

## pseudocode

```c
__int64 load__SetAccessible_Element_DirectUI__QEAAJ_N_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002686  lea     rax, __imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x18000268d  jmp     __tailMerge_dui70_dll
```
