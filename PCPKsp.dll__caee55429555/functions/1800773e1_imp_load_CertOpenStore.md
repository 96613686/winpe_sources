# __imp_load_CertOpenStore

- ea: `0x1800773e1`
- end: `0x1800773ed`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180077362`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x1800773e1`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1800773e1  lea     rax, __imp_CertOpenStore
0x1800773e8  jmp     __tailMerge_crypt32_dll
```
