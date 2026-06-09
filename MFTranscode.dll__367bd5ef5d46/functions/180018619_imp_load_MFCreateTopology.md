# __imp_load_MFCreateTopology

- ea: `0x180018619`
- end: `0x180018625`
- name: `__imp_load_MFCreateTopology`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180018564`

## import_xrefs

- `MFCORE!MFCreateTopology` at `0x180018619`

## pseudocode

```c
__int64 load_MFCreateTopology()
{
  return _tailMerge_mfcore_dll();
}

```

## disassembly

```asm
0x180018619  lea     rax, __imp_MFCreateTopology
0x180018620  jmp     __tailMerge_mfcore_dll
```
