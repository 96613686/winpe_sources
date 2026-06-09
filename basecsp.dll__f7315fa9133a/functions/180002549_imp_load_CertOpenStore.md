# __imp_load_CertOpenStore

- ea: `0x180002549`
- end: `0x180002555`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002300`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180002549`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180002549  lea     rax, __imp_CertOpenStore
0x180002550  jmp     __tailMerge_crypt32_dll
```
