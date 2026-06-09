# __imp_load_MFCreateAttributes

- ea: `0x180055639`
- end: `0x180055645`
- name: `__imp_load_MFCreateAttributes`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004dd1a`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180055639`

## pseudocode

```c
__int64 load_MFCreateAttributes()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180055639  lea     rax, __imp_MFCreateAttributes
0x180055640  jmp     __tailMerge_mfplat_dll
```
