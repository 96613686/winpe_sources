# __imp_load_SdbOpenDatabase

- ea: `0x180002513`
- end: `0x18000251f`
- name: `__imp_load_SdbOpenDatabase`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002470`

## import_xrefs

- `apphelp!SdbOpenDatabase` at `0x180002513`

## pseudocode

```c
__int64 load_SdbOpenDatabase()
{
  return _tailMerge_apphelp_dll();
}

```

## disassembly

```asm
0x180002513  lea     rax, __imp_SdbOpenDatabase
0x18000251a  jmp     __tailMerge_apphelp_dll
```
