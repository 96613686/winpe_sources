# DirectUI::Element::GetAccessibleImpl(IAccessible * *)

- ea: `0x180002c30`
- end: `0x180002c36`
- name: `?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z_0`
- size: `6`
- prototype: `int __fastcall(DirectUI::Element *this, struct IAccessible **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z` at `0x180002c30`

## pseudocode

```c
// attributes: thunk
int __fastcall DirectUI::Element::GetAccessibleImpl(DirectUI::Element *this, struct IAccessible **a2)
{
  return __imp_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z(this, a2);
}

```

## disassembly

```asm
0x180002c30  jmp     cs:__imp_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z
```
