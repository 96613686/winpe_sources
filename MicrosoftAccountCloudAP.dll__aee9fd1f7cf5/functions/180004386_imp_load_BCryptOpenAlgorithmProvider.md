# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180004386`
- end: `0x180004392`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003c62`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180004386`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180004386  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x18000438d  jmp     __tailMerge_bcrypt_dll
```
