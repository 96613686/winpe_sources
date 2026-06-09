# __imp_load_BiQueryBrokeredEvent

- ea: `0x1800166b9`
- end: `0x1800166c5`
- name: `__imp_load_BiQueryBrokeredEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800165e0`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiQueryBrokeredEvent` at `0x1800166b9`

## pseudocode

```c
__int64 load_BiQueryBrokeredEvent()
{
  return _tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll();
}

```

## disassembly

```asm
0x1800166b9  lea     rax, __imp_BiQueryBrokeredEvent
0x1800166c0  jmp     __tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll
```
