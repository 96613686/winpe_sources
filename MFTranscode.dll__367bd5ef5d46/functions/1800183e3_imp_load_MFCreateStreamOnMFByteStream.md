# __imp_load_MFCreateStreamOnMFByteStream

- ea: `0x1800183e3`
- end: `0x1800183ef`
- name: `__imp_load_MFCreateStreamOnMFByteStream`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateStreamOnMFByteStream` at `0x1800183e3`

## pseudocode

```c
__int64 load_MFCreateStreamOnMFByteStream()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x1800183e3  lea     rax, __imp_MFCreateStreamOnMFByteStream
0x1800183ea  jmp     __tailMerge_mfplat_dll
```
