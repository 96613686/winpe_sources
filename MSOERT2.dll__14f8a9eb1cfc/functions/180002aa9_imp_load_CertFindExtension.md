# __imp_load_CertFindExtension

- ea: `0x180002aa9`
- end: `0x180002ab5`
- name: `__imp_load_CertFindExtension`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800029d0`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180002aa9`

## pseudocode

```c
__int64 load_CertFindExtension()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180002aa9  lea     rax, __imp_CertFindExtension
0x180002ab0  jmp     __tailMerge_crypt32_dll
```
