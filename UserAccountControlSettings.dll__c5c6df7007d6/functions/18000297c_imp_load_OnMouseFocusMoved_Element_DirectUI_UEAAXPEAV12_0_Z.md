# __imp_load_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z

- ea: `0x18000297c`
- end: `0x180002988`
- name: `__imp_load_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z` at `0x18000297c`

## pseudocode

```c
__int64 load__OnMouseFocusMoved_Element_DirectUI__UEAAXPEAV12_0_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000297c  lea     rax, __imp_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z; DirectUI::Element::OnMouseFocusMoved(DirectUI::Element *,DirectUI::Element *)
0x180002983  jmp     __tailMerge_dui70_dll
```
