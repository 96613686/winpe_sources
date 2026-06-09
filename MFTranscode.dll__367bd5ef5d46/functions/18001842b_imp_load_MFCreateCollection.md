# __imp_load_MFCreateCollection

- ea: `0x18001842b`
- end: `0x180018437`
- name: `__imp_load_MFCreateCollection`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateCollection` at `0x18001842b`

## pseudocode

```c
__int64 load_MFCreateCollection()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x18001842b  lea     rax, __imp_MFCreateCollection
0x180018432  jmp     __tailMerge_mfplat_dll
```
