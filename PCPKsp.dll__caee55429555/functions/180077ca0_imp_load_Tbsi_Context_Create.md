# __imp_load_Tbsi_Context_Create

- ea: `0x180077ca0`
- end: `0x180077cac`
- name: `__imp_load_Tbsi_Context_Create`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180077c0f`

## import_xrefs

- `tbs!Tbsi_Context_Create` at `0x180077ca0`

## pseudocode

```c
__int64 load_Tbsi_Context_Create()
{
  return _tailMerge_tbs_dll();
}

```

## disassembly

```asm
0x180077ca0  lea     rax, __imp_Tbsi_Context_Create
0x180077ca7  jmp     __tailMerge_tbs_dll
```
