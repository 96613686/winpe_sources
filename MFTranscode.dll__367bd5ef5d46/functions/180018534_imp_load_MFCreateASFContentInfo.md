# __imp_load_MFCreateASFContentInfo

- ea: `0x180018534`
- end: `0x180018540`
- name: `__imp_load_MFCreateASFContentInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800184a3`

## import_xrefs

- `mfasfsrcsnk!MFCreateASFContentInfo` at `0x180018534`

## pseudocode

```c
__int64 load_MFCreateASFContentInfo()
{
  return _tailMerge_mfasfsrcsnk_dll();
}

```

## disassembly

```asm
0x180018534  lea     rax, __imp_MFCreateASFContentInfo
0x18001853b  jmp     __tailMerge_mfasfsrcsnk_dll
```
