# __imp_load_MFCreateAsyncResult

- ea: `0x180018365`
- end: `0x180018371`
- name: `__imp_load_MFCreateAsyncResult`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x180018365`

## pseudocode

```c
__int64 load_MFCreateAsyncResult()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180018365  lea     rax, __imp_MFCreateAsyncResult
0x18001836c  jmp     __tailMerge_mfplat_dll
```
