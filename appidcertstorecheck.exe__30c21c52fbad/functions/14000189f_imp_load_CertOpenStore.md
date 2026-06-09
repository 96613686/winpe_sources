# __imp_load_CertOpenStore

- ea: `0x14000189f`
- end: `0x1400018ab`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001820`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x14000189f`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x14000189f  lea     rax, __imp_CertOpenStore
0x1400018a6  jmp     __tailMerge_crypt32_dll
```
