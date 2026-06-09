# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x18007717f`
- end: `0x18007718b`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800770e2`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007717f`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18007717f  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x180077186  jmp     __tailMerge_bcrypt_dll
```
