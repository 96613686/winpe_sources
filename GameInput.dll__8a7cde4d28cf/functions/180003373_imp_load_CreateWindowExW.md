# __imp_load_CreateWindowExW

- ea: `0x180003373`
- end: `0x18000337f`
- name: `__imp_load_CreateWindowExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800032d0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180003373`

## pseudocode

```c
__int64 load_CreateWindowExW()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003373  lea     rax, __imp_CreateWindowExW
0x18000337a  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
