# __imp_load_CertOpenStore

- ea: `0x180002040`
- end: `0x18000204c`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001fbc`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180002040`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180002040  lea     rax, __imp_CertOpenStore
0x180002047  jmp     __tailMerge_crypt32_dll
```
