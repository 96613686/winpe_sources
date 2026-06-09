# __imp_load_GetCustomRegRootPath

- ea: `0x18002ad91`
- end: `0x18002ad9d`
- name: `__imp_load_GetCustomRegRootPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002ad12`

## import_xrefs

- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18002ad91`

## pseudocode

```c
__int64 load_GetCustomRegRootPath()
{
  return _tailMerge_ext_ms_win_networking_wlanstorage_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002ad91  lea     rax, __imp_GetCustomRegRootPath
0x18002ad98  jmp     __tailMerge_ext_ms_win_networking_wlanstorage_l1_1_0_dll
```
