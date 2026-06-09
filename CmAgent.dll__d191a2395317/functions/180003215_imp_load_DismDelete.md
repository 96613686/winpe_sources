# __imp_load_DismDelete

- ea: `0x180003215`
- end: `0x180003221`
- name: `__imp_load_DismDelete`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003160`

## import_xrefs

- `DismApi!DismDelete` at `0x180003215`

## pseudocode

```c
__int64 load_DismDelete()
{
  return _tailMerge_dismapi_dll();
}

```

## disassembly

```asm
0x180003215  lea     rax, __imp_DismDelete
0x18000321c  jmp     __tailMerge_dismapi_dll
```
