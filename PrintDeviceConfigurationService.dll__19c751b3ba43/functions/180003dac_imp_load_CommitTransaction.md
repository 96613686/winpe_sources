# __imp_load_CommitTransaction

- ea: `0x180003dac`
- end: `0x180003db8`
- name: `__imp_load_CommitTransaction`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003d1b`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x180003dac`

## pseudocode

```c
__int64 load_CommitTransaction()
{
  return _tailMerge_ktmw32_dll();
}

```

## disassembly

```asm
0x180003dac  lea     rax, __imp_CommitTransaction
0x180003db3  jmp     __tailMerge_ktmw32_dll
```
