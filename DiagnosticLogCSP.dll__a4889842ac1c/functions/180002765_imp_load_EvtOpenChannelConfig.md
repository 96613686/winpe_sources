# __imp_load_EvtOpenChannelConfig

- ea: `0x180002765`
- end: `0x180002771`
- name: `__imp_load_EvtOpenChannelConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800026e6`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x180002765`

## pseudocode

```c
__int64 load_EvtOpenChannelConfig()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002765  lea     rax, __imp_EvtOpenChannelConfig
0x18000276c  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll
```
