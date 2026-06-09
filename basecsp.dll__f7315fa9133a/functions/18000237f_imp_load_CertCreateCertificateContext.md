# __imp_load_CertCreateCertificateContext

- ea: `0x18000237f`
- end: `0x18000238b`
- name: `__imp_load_CertCreateCertificateContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002300`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x18000237f`

## pseudocode

```c
__int64 load_CertCreateCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x18000237f  lea     rax, __imp_CertCreateCertificateContext
0x180002386  jmp     __tailMerge_crypt32_dll
```
