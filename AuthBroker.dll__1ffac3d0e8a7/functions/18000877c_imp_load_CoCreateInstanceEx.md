# __imp_load_CoCreateInstanceEx

- ea: `0x18000877c`
- end: `0x180008788`
- name: `__imp_load_CoCreateInstanceEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008643`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18000877c`

## pseudocode

```c
__int64 load_CoCreateInstanceEx()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000877c  lea     rax, __imp_CoCreateInstanceEx
0x180008783  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
