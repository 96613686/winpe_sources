# __imp_load_CoMarshalInterThreadInterfaceInStream

- ea: `0x180008b58`
- end: `0x180008b64`
- name: `__imp_load_CoMarshalInterThreadInterfaceInStream`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008643`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180008b58`

## pseudocode

```c
__int64 load_CoMarshalInterThreadInterfaceInStream()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180008b58  lea     rax, __imp_CoMarshalInterThreadInterfaceInStream
0x180008b5f  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
