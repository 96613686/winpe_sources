# __imp_load_FwRegDeleteKey

- ea: `0x1800207f6`
- end: `0x180020802`
- name: `__imp_load_FwRegDeleteKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwRegDeleteKey` at `0x1800207f6`

## pseudocode

```c
__int64 load_FwRegDeleteKey()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800207f6  lea     rax, __imp_FwRegDeleteKey
0x1800207fd  jmp     __tailMerge_fwbase_dll
```
