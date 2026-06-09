# __imp_load_CertCreateCertificateContext

- ea: `0x1400018e7`
- end: `0x1400018f3`
- name: `__imp_load_CertCreateCertificateContext`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001820`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x1400018e7`

## pseudocode

```c
__int64 load_CertCreateCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1400018e7  lea     rax, __imp_CertCreateCertificateContext
0x1400018ee  jmp     __tailMerge_crypt32_dll
```
