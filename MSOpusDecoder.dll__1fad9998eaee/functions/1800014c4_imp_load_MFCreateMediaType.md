# __imp_load_MFCreateMediaType

- ea: `0x1800014c4`
- end: `0x1800014d0`
- name: `__imp_load_MFCreateMediaType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001445`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800014c4`

## pseudocode

```c
__int64 load_MFCreateMediaType()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x1800014c4  lea     rax, __imp_MFCreateMediaType
0x1800014cb  jmp     __tailMerge_mfplat_dll
```
