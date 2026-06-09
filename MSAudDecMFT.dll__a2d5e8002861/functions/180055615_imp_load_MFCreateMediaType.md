# __imp_load_MFCreateMediaType

- ea: `0x180055615`
- end: `0x180055621`
- name: `__imp_load_MFCreateMediaType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004dd1a`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180055615`

## pseudocode

```c
__int64 load_MFCreateMediaType()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180055615  lea     rax, __imp_MFCreateMediaType
0x18005561c  jmp     __tailMerge_mfplat_dll
```
