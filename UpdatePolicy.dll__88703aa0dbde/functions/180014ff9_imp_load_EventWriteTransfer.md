# __imp_load_EventWriteTransfer

- ea: `0x180014ff9`
- end: `0x180015005`
- name: `__imp_load_EventWriteTransfer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014f7a`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014ff9`

## pseudocode

```c
__int64 load_EventWriteTransfer()
{
  return _tailMerge_api_ms_win_eventing_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x180014ff9  lea     rax, __imp_EventWriteTransfer
0x180015000  jmp     __tailMerge_api_ms_win_eventing_provider_l1_1_0_dll
```
