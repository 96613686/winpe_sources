# __imp_load_MFCreateMediaSession

- ea: `0x180018607`
- end: `0x180018613`
- name: `__imp_load_MFCreateMediaSession`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180018564`

## import_xrefs

- `MFCORE!MFCreateMediaSession` at `0x180018607`

## pseudocode

```c
__int64 load_MFCreateMediaSession()
{
  return _tailMerge_mfcore_dll();
}

```

## disassembly

```asm
0x180018607  lea     rax, __imp_MFCreateMediaSession
0x18001860e  jmp     __tailMerge_mfcore_dll
```
