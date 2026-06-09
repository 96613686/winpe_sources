# __imp_load_UpdateWindow

- ea: `0x140001fad`
- end: `0x140001fb9`
- name: `__imp_load_UpdateWindow`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x140001f2e`

## import_xrefs

- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x140001fad`

## pseudocode

```c
__int64 load_UpdateWindow()
{
  return _tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x140001fad  lea     rax, __imp_UpdateWindow
0x140001fb4  jmp     __tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll
```
