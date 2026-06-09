# __imp_load_CertAddCertificateContextToStore

- ea: `0x1400018d5`
- end: `0x1400018e1`
- name: `__imp_load_CertAddCertificateContextToStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001820`

## import_xrefs

- `CRYPT32!CertAddCertificateContextToStore` at `0x1400018d5`

## pseudocode

```c
__int64 load_CertAddCertificateContextToStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1400018d5  lea     rax, __imp_CertAddCertificateContextToStore
0x1400018dc  jmp     __tailMerge_crypt32_dll
```
