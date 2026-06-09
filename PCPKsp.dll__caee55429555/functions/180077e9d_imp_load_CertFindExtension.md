# __imp_load_CertFindExtension

- ea: `0x180077e9d`
- end: `0x180077ea9`
- name: `__imp_load_CertFindExtension`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180077362`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180077e9d`

## pseudocode

```c
__int64 load_CertFindExtension()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180077e9d  lea     rax, __imp_CertFindExtension
0x180077ea4  jmp     __tailMerge_crypt32_dll
```
