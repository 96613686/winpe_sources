# __imp_load_CertCloseStore

- ea: `0x1400018c3`
- end: `0x1400018cf`
- name: `__imp_load_CertCloseStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001820`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x1400018c3`

## pseudocode

```c
__int64 load_CertCloseStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1400018c3  lea     rax, __imp_CertCloseStore
0x1400018ca  jmp     __tailMerge_crypt32_dll
```
