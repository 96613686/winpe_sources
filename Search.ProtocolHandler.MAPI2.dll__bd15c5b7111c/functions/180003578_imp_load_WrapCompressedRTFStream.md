# __imp_load_WrapCompressedRTFStream

- ea: `0x180003578`
- end: `0x180003584`
- name: `__imp_load_WrapCompressedRTFStream`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800034b1`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_WrapCompressedRTFStream` at `0x180003578`

## pseudocode

```c
__int64 load_WrapCompressedRTFStream()
{
  return _tailMerge_ext_ms_win_mapi_mapi32_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003578  lea     rax, __imp_WrapCompressedRTFStream
0x18000357f  jmp     __tailMerge_ext_ms_win_mapi_mapi32_l1_1_0_dll
```
