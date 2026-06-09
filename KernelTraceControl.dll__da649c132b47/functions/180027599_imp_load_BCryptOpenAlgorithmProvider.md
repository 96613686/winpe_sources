# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180027599`
- end: `0x1800275a5`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800275a5`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180027599`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180027599  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x1800275a0  jmp     $+5
```
