# __imp_load_EvtSetChannelConfigProperty

- ea: `0x180002856`
- end: `0x180002862`
- name: `__imp_load_EvtSetChannelConfigProperty`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800027d7`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x180002856`

## pseudocode

```c
__int64 load_EvtSetChannelConfigProperty()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll();
}

```

## disassembly

```asm
0x180002856  lea     rax, __imp_EvtSetChannelConfigProperty
0x18000285d  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll
```
