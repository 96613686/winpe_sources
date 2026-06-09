# __imp_load_FwRegOpenKey

- ea: `0x1800206d6`
- end: `0x1800206e2`
- name: `__imp_load_FwRegOpenKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x1800206d6`

## pseudocode

```c
__int64 load_FwRegOpenKey()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800206d6  lea     rax, __imp_FwRegOpenKey
0x1800206dd  jmp     __tailMerge_fwbase_dll
```
