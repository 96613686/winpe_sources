# __imp_load_RegCreateKeyTransactedW

- ea: `0x180002690`
- end: `0x18000269c`
- name: `__imp_load_RegCreateKeyTransactedW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800025ac`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180002690`

## pseudocode

```c
__int64 load_RegCreateKeyTransactedW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002690  lea     rax, __imp_RegCreateKeyTransactedW
0x180002697  jmp     __tailMerge_advapi32_dll
```
