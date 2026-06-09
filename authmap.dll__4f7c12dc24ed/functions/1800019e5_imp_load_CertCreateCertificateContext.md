# __imp_load_CertCreateCertificateContext

- ea: `0x1800019e5`
- end: `0x1800019f1`
- name: `__imp_load_CertCreateCertificateContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001930`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x1800019e5`

## pseudocode

```c
__int64 load_CertCreateCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1800019e5  lea     rax, __imp_CertCreateCertificateContext
0x1800019ec  jmp     __tailMerge_crypt32_dll
```
