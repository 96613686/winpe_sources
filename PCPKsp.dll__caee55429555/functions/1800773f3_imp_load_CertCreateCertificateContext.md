# __imp_load_CertCreateCertificateContext

- ea: `0x1800773f3`
- end: `0x1800773ff`
- name: `__imp_load_CertCreateCertificateContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180077362`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x1800773f3`

## pseudocode

```c
__int64 load_CertCreateCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1800773f3  lea     rax, __imp_CertCreateCertificateContext
0x1800773fa  jmp     __tailMerge_crypt32_dll
```
