# __imp_load_UpdateWindow

- ea: `0x1400043df`
- end: `0x1400043eb`
- name: `__imp_load_UpdateWindow`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x140004360`

## import_xrefs

- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400043df`

## pseudocode

```c
__int64 load_UpdateWindow()
{
  return _tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400043df  lea     rax, __imp_UpdateWindow
0x1400043e6  jmp     __tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll
```
