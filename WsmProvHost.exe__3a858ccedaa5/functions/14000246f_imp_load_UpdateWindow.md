# __imp_load_UpdateWindow

- ea: `0x14000246f`
- end: `0x14000247b`
- name: `__imp_load_UpdateWindow`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400023f0`

## import_xrefs

- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x14000246f`

## pseudocode

```c
__int64 load_UpdateWindow()
{
  return _tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000246f  lea     rax, __imp_UpdateWindow
0x140002476  jmp     __tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll
```
