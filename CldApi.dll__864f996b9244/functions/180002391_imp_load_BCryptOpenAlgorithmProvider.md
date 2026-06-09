# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180002391`
- end: `0x18000239d`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002300`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180002391`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180002391  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x180002398  jmp     __tailMerge_bcrypt_dll
```
