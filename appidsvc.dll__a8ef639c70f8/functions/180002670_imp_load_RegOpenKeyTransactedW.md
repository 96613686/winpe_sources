# __imp_load_RegOpenKeyTransactedW

- ea: `0x180002670`
- end: `0x18000267c`
- name: `__imp_load_RegOpenKeyTransactedW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800025ac`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x180002670`

## pseudocode

```c
__int64 load_RegOpenKeyTransactedW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002670  lea     rax, __imp_RegOpenKeyTransactedW
0x180002677  jmp     __tailMerge_advapi32_dll
```
