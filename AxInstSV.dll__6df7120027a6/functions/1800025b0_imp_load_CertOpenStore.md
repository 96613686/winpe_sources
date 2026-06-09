# __imp_load_CertOpenStore

- ea: `0x1800025b0`
- end: `0x1800025bc`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000251f`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x1800025b0`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1800025b0  lea     rax, __imp_CertOpenStore
0x1800025b7  jmp     __tailMerge_crypt32_dll
```
