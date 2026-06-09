# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180001a21`
- end: `0x180001a2d`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001990`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001a21`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180001a21  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x180001a28  jmp     __tailMerge_bcrypt_dll
```
