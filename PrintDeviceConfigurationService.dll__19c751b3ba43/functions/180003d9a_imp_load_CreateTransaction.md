# __imp_load_CreateTransaction

- ea: `0x180003d9a`
- end: `0x180003da6`
- name: `__imp_load_CreateTransaction`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003d1b`

## import_xrefs

- `ktmw32!CreateTransaction` at `0x180003d9a`

## pseudocode

```c
__int64 load_CreateTransaction()
{
  return _tailMerge_ktmw32_dll();
}

```

## disassembly

```asm
0x180003d9a  lea     rax, __imp_CreateTransaction
0x180003da1  jmp     __tailMerge_ktmw32_dll
```
