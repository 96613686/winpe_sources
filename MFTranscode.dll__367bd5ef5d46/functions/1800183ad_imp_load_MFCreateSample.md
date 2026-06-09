# __imp_load_MFCreateSample

- ea: `0x1800183ad`
- end: `0x1800183b9`
- name: `__imp_load_MFCreateSample`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x1800183ad`

## pseudocode

```c
__int64 load_MFCreateSample()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x1800183ad  lea     rax, __imp_MFCreateSample
0x1800183b4  jmp     __tailMerge_mfplat_dll
```
