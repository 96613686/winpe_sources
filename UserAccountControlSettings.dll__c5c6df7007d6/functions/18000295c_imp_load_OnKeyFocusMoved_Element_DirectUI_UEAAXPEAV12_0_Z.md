# __imp_load_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z

- ea: `0x18000295c`
- end: `0x180002968`
- name: `__imp_load_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z` at `0x18000295c`

## pseudocode

```c
__int64 load__OnKeyFocusMoved_Element_DirectUI__UEAAXPEAV12_0_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000295c  lea     rax, __imp_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z; DirectUI::Element::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)
0x180002963  jmp     __tailMerge_dui70_dll
```
