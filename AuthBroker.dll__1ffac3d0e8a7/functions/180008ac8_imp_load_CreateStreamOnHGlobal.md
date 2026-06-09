# __imp_load_CreateStreamOnHGlobal

- ea: `0x180008ac8`
- end: `0x180008ad4`
- name: `__imp_load_CreateStreamOnHGlobal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008643`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180008ac8`

## pseudocode

```c
__int64 load_CreateStreamOnHGlobal()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180008ac8  lea     rax, __imp_CreateStreamOnHGlobal
0x180008acf  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
