# __imp_load_MFCreateASFProfile

- ea: `0x180018522`
- end: `0x18001852e`
- name: `__imp_load_MFCreateASFProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800184a3`

## import_xrefs

- `mfasfsrcsnk!MFCreateASFProfile` at `0x180018522`

## pseudocode

```c
__int64 load_MFCreateASFProfile()
{
  return _tailMerge_mfasfsrcsnk_dll();
}

```

## disassembly

```asm
0x180018522  lea     rax, __imp_MFCreateASFProfile
0x180018529  jmp     __tailMerge_mfasfsrcsnk_dll
```
