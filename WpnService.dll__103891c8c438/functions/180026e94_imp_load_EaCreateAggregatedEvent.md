# __imp_load_EaCreateAggregatedEvent

- ea: `0x180026e94`
- end: `0x180026ea0`
- name: `__imp_load_EaCreateAggregatedEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180026e15`

## import_xrefs

- `EventAggregation!EaCreateAggregatedEvent` at `0x180026e94`

## pseudocode

```c
__int64 load_EaCreateAggregatedEvent()
{
  return _tailMerge_eventaggregation_dll();
}

```

## disassembly

```asm
0x180026e94  lea     rax, __imp_EaCreateAggregatedEvent
0x180026e9b  jmp     __tailMerge_eventaggregation_dll
```
