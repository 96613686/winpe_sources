# __imp_load_CreateStreamOnHGlobal

- ea: `0x1800022b4`
- end: `0x1800022c0`
- name: `__imp_load_CreateStreamOnHGlobal`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e87`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800022b4`

## pseudocode

```c
__int64 load_CreateStreamOnHGlobal()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800022b4  lea     rax, __imp_CreateStreamOnHGlobal
0x1800022bb  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
