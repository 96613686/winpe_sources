# __imp_load_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z

- ea: `0x180002c3c`
- end: `0x180002c48`
- name: `__imp_load_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z` at `0x180002c3c`

## pseudocode

```c
__int64 load__GetAccessibleImpl_Element_DirectUI__UEAAJPEAPEAUIAccessible___Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002c3c  lea     rax, __imp_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z; DirectUI::Element::GetAccessibleImpl(IAccessible * *)
0x180002c43  jmp     __tailMerge_dui70_dll
```
