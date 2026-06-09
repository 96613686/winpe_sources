# __imp_load_FwRegSetString

- ea: `0x180020874`
- end: `0x180020880`
- name: `__imp_load_FwRegSetString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwRegSetString` at `0x180020874`

## pseudocode

```c
__int64 load_FwRegSetString()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020874  lea     rax, __imp_FwRegSetString
0x18002087b  jmp     __tailMerge_fwbase_dll
```
