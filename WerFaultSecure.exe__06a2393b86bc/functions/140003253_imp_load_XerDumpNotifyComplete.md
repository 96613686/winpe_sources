# __imp_load_XerDumpNotifyComplete

- ea: `0x140003253`
- end: `0x14000325f`
- name: `__imp_load_XerDumpNotifyComplete`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400031c2`

## import_xrefs

- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x140003253`

## pseudocode

```c
__int64 load_XerDumpNotifyComplete()
{
  return _tailMerge_ext_ms_win_wer_xbox_l1_1_1_dll();
}

```

## disassembly

```asm
0x140003253  lea     rax, __imp_XerDumpNotifyComplete
0x14000325a  jmp     __tailMerge_ext_ms_win_wer_xbox_l1_1_1_dll
```
