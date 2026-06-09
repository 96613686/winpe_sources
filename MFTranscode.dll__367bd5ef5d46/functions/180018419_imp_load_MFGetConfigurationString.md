# __imp_load_MFGetConfigurationString

- ea: `0x180018419`
- end: `0x180018425`
- name: `__imp_load_MFGetConfigurationString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFGetConfigurationString` at `0x180018419`

## pseudocode

```c
__int64 load_MFGetConfigurationString()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180018419  lea     rax, __imp_MFGetConfigurationString
0x180018420  jmp     __tailMerge_mfplat_dll
```
