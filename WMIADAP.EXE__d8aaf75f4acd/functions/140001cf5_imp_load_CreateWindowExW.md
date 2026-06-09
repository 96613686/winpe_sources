# __imp_load_CreateWindowExW

- ea: `0x140001cf5`
- end: `0x140001d01`
- name: `__imp_load_CreateWindowExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001c76`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x140001cf5`

## pseudocode

```c
__int64 load_CreateWindowExW()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x140001cf5  lea     rax, __imp_CreateWindowExW
0x140001cfc  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
