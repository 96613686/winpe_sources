# __imp_load_CertFreeCertificateChain

- ea: `0x14000190b`
- end: `0x140001917`
- name: `__imp_load_CertFreeCertificateChain`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001820`

## import_xrefs

- `CRYPT32!CertFreeCertificateChain` at `0x14000190b`

## pseudocode

```c
__int64 load_CertFreeCertificateChain()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x14000190b  lea     rax, __imp_CertFreeCertificateChain
0x140001912  jmp     __tailMerge_crypt32_dll
```
