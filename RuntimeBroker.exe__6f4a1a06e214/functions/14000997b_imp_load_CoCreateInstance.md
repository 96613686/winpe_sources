# __imp_load_CoCreateInstance

- ea: `0x14000997b`
- end: `0x140009987`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000969a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000997b`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000997b  lea     rax, __imp_CoCreateInstance
0x140009982  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
