# __imp_load_MFCreateAttributes

- ea: `0x180005c1f`
- end: `0x180005c2b`
- name: `__imp_load_MFCreateAttributes`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005ba0`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180005c1f`

## pseudocode

```c
__int64 load_MFCreateAttributes()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180005c1f  lea     rax, __imp_MFCreateAttributes
0x180005c26  jmp     __tailMerge_mfplat_dll
```
