# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x1800026e1`
- end: `0x1800026ed`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000218a`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800026e1`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x1800026e1  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x1800026e8  jmp     __tailMerge_bcrypt_dll
```
