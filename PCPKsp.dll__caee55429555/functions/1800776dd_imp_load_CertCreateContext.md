# __imp_load_CertCreateContext

- ea: `0x1800776dd`
- end: `0x1800776e9`
- name: `__imp_load_CertCreateContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180077362`

## import_xrefs

- `CRYPT32!CertCreateContext` at `0x1800776dd`

## pseudocode

```c
__int64 load_CertCreateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1800776dd  lea     rax, __imp_CertCreateContext
0x1800776e4  jmp     __tailMerge_crypt32_dll
```
