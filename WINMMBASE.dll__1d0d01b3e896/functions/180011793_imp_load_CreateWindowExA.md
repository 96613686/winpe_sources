# __imp_load_CreateWindowExA

- ea: `0x180011793`
- end: `0x18001179f`
- name: `__imp_load_CreateWindowExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011702`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x180011793`

## pseudocode

```c
__int64 load_CreateWindowExA()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x180011793  lea     rax, __imp_CreateWindowExA
0x18001179a  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
