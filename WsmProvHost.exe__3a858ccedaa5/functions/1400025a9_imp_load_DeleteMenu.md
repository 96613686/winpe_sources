# __imp_load_DeleteMenu

- ea: `0x1400025a9`
- end: `0x1400025b5`
- name: `__imp_load_DeleteMenu`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002518`

## import_xrefs

- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1400025a9`

## pseudocode

```c
__int64 load_DeleteMenu()
{
  return _tailMerge_ext_ms_win_ntuser_menu_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400025a9  lea     rax, __imp_DeleteMenu
0x1400025b0  jmp     __tailMerge_ext_ms_win_ntuser_menu_l1_1_0_dll
```
