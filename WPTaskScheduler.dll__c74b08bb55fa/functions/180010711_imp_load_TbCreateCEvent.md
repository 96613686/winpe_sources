# __imp_load_TbCreateCEvent

- ea: `0x180010711`
- end: `0x18001071d`
- name: `__imp_load_TbCreateCEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010680`

## import_xrefs

- `TimeBrokerClient!TbCreateCEvent` at `0x180010711`

## pseudocode

```c
__int64 load_TbCreateCEvent()
{
  return _tailMerge_timebrokerclient_dll();
}

```

## disassembly

```asm
0x180010711  lea     rax, __imp_TbCreateCEvent
0x180010718  jmp     __tailMerge_timebrokerclient_dll
```
