# __imp_load_NCryptOpenStorageProvider

- ea: `0x180077544`
- end: `0x180077550`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18007747d`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180077544`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x180077544  lea     rax, __imp_NCryptOpenStorageProvider
0x18007754b  jmp     __tailMerge_ncrypt_dll
```
