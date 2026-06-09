# __imp_load_UuidCreate

- ea: `0x18000ac54`
- end: `0x18000ac60`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000abb1`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000ac54`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000ac54  lea     rax, __imp_UuidCreate
0x18000ac5b  jmp     __tailMerge_rpcrt4_dll
```
