# __imp_load_MFCreateMediaType

- ea: `0x18001831d`
- end: `0x180018329`
- name: `__imp_load_MFCreateMediaType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001831d`

## pseudocode

```c
__int64 load_MFCreateMediaType()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x18001831d  lea     rax, __imp_MFCreateMediaType
0x180018324  jmp     __tailMerge_mfplat_dll
```
