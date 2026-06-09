# __imp_load_MFCreateAlignedMemoryBuffer

- ea: `0x1800183bf`
- end: `0x1800183cb`
- name: `__imp_load_MFCreateAlignedMemoryBuffer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x1800183bf`

## pseudocode

```c
__int64 load_MFCreateAlignedMemoryBuffer()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x1800183bf  lea     rax, __imp_MFCreateAlignedMemoryBuffer
0x1800183c6  jmp     __tailMerge_mfplat_dll
```
