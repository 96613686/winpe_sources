# __imp_load_BiEnumerateBrokeredEvents

- ea: `0x1800166cb`
- end: `0x1800166d7`
- name: `__imp_load_BiEnumerateBrokeredEvents`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800165e0`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiEnumerateBrokeredEvents` at `0x1800166cb`

## pseudocode

```c
__int64 load_BiEnumerateBrokeredEvents()
{
  return _tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll();
}

```

## disassembly

```asm
0x1800166cb  lea     rax, __imp_BiEnumerateBrokeredEvents
0x1800166d2  jmp     __tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll
```
