# __imp_load_CLSIDFromString

- ea: `0x18002027e`
- end: `0x18002028a`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002003a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002027e`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002027e  lea     rax, __imp_CLSIDFromString
0x180020285  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
