# __imp_load_SetProtocolProperty

- ea: `0x180004439`
- end: `0x180004445`
- name: `__imp_load_SetProtocolProperty`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800043ba`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-4!SetProtocolProperty` at `0x180004439`

## pseudocode

```c
__int64 load_SetProtocolProperty()
{
  return _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_4_dll();
}

```

## disassembly

```asm
0x180004439  lea     rax, __imp_SetProtocolProperty
0x180004440  jmp     __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_4_dll
```
