# __imp_load_MFCreateAttributes

- ea: `0x18001830b`
- end: `0x180018317`
- name: `__imp_load_MFCreateAttributes`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18001830b`

## pseudocode

```c
__int64 load_MFCreateAttributes()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x18001830b  lea     rax, __imp_MFCreateAttributes
0x180018312  jmp     __tailMerge_mfplat_dll
```
