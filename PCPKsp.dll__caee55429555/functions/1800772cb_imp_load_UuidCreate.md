# __imp_load_UuidCreate

- ea: `0x1800772cb`
- end: `0x1800772d7`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18007724c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800772cb`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800772cb  lea     rax, __imp_UuidCreate
0x1800772d2  jmp     __tailMerge_rpcrt4_dll
```
