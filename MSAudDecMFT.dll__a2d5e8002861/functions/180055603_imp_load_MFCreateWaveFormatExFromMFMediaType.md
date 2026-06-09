# __imp_load_MFCreateWaveFormatExFromMFMediaType

- ea: `0x180055603`
- end: `0x18005560f`
- name: `__imp_load_MFCreateWaveFormatExFromMFMediaType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004dd1a`

## import_xrefs

- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x180055603`

## pseudocode

```c
__int64 load_MFCreateWaveFormatExFromMFMediaType()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180055603  lea     rax, __imp_MFCreateWaveFormatExFromMFMediaType
0x18005560a  jmp     __tailMerge_mfplat_dll
```
