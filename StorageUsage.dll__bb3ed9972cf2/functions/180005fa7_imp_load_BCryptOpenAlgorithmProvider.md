# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180005fa7`
- end: `0x180005fb3`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005eaa`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180005fa7`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180005fa7  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x180005fae  jmp     __tailMerge_bcrypt_dll
```
