# __imp_load_MFCreateSourceResolver

- ea: `0x1800183d1`
- end: `0x1800183dd`
- name: `__imp_load_MFCreateSourceResolver`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateSourceResolver` at `0x1800183d1`

## pseudocode

```c
__int64 load_MFCreateSourceResolver()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x1800183d1  lea     rax, __imp_MFCreateSourceResolver
0x1800183d8  jmp     __tailMerge_mfplat_dll
```
