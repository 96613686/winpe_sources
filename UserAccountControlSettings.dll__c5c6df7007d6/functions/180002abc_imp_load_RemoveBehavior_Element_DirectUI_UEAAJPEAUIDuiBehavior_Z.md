# __imp_load_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z

- ea: `0x180002abc`
- end: `0x180002ac8`
- name: `__imp_load_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z` at `0x180002abc`

## pseudocode

```c
__int64 load__RemoveBehavior_Element_DirectUI__UEAAJPEAUIDuiBehavior___Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002abc  lea     rax, __imp_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z; DirectUI::Element::RemoveBehavior(IDuiBehavior *)
0x180002ac3  jmp     __tailMerge_dui70_dll
```
