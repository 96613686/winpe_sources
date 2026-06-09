# __imp_load_MFCreateASFMediaSinkActivateFromByteStream

- ea: `0x180018546`
- end: `0x180018552`
- name: `__imp_load_MFCreateASFMediaSinkActivateFromByteStream`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800184a3`

## import_xrefs

- `mfasfsrcsnk!MFCreateASFMediaSinkActivateFromByteStream` at `0x180018546`

## pseudocode

```c
__int64 load_MFCreateASFMediaSinkActivateFromByteStream()
{
  return _tailMerge_mfasfsrcsnk_dll();
}

```

## disassembly

```asm
0x180018546  lea     rax, __imp_MFCreateASFMediaSinkActivateFromByteStream
0x18001854d  jmp     __tailMerge_mfasfsrcsnk_dll
```
