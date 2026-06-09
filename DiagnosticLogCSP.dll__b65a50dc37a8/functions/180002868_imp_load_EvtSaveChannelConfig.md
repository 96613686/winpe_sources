# __imp_load_EvtSaveChannelConfig

- ea: `0x180002868`
- end: `0x180002874`
- name: `__imp_load_EvtSaveChannelConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800027d7`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x180002868`

## pseudocode

```c
__int64 load_EvtSaveChannelConfig()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll();
}

```

## disassembly

```asm
0x180002868  lea     rax, __imp_EvtSaveChannelConfig
0x18000286f  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll
```
