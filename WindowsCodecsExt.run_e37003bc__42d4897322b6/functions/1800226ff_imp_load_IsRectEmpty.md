# __imp_load_IsRectEmpty

- ea: `0x1800226ff`
- end: `0x18002270b`
- name: `__imp_load_IsRectEmpty`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002266e`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x1800226ff`

## pseudocode

```c
__int64 load_IsRectEmpty()
{
  return _tailMerge_ext_ms_win_ntuser_rectangle_ext_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800226ff  lea     rax, __imp_IsRectEmpty
0x180022706  jmp     __tailMerge_ext_ms_win_ntuser_rectangle_ext_l1_1_0_dll
```
