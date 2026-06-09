# __imp_load_CertFreeCertificateContext

- ea: `0x1400018b1`
- end: `0x1400018bd`
- name: `__imp_load_CertFreeCertificateContext`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001820`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x1400018b1`

## pseudocode

```c
__int64 load_CertFreeCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1400018b1  lea     rax, __imp_CertFreeCertificateContext
0x1400018b8  jmp     __tailMerge_crypt32_dll
```
