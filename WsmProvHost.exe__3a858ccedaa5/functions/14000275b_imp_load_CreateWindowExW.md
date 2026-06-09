# __imp_load_CreateWindowExW

- ea: `0x14000275b`
- end: `0x140002767`
- name: `__imp_load_CreateWindowExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400026ca`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000275b`

## pseudocode

```c
__int64 load_CreateWindowExW()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000275b  lea     rax, __imp_CreateWindowExW
0x140002762  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
