# __imp_load_CertGetCertificateChain

- ea: `0x1400018f9`
- end: `0x140001905`
- name: `__imp_load_CertGetCertificateChain`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001820`

## import_xrefs

- `CRYPT32!CertGetCertificateChain` at `0x1400018f9`

## pseudocode

```c
__int64 load_CertGetCertificateChain()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1400018f9  lea     rax, __imp_CertGetCertificateChain
0x140001900  jmp     __tailMerge_crypt32_dll
```
