# __imp_load_MFCreateASFMediaSinkActivate

- ea: `0x180018558`
- end: `0x180018564`
- name: `__imp_load_MFCreateASFMediaSinkActivate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800184a3`

## import_xrefs

- `mfasfsrcsnk!MFCreateASFMediaSinkActivate` at `0x180018558`

## pseudocode

```c
__int64 load_MFCreateASFMediaSinkActivate()
{
  return _tailMerge_mfasfsrcsnk_dll();
}

```

## disassembly

```asm
0x180018558  lea     rax, __imp_MFCreateASFMediaSinkActivate
0x18001855f  jmp     __tailMerge_mfasfsrcsnk_dll
```
