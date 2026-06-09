# __imp_load_DafCreateAssociationContext

- ea: `0x1800028b8`
- end: `0x1800028c4`
- name: `__imp_load_DafCreateAssociationContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002839`

## import_xrefs

- `deviceassociation!DafCreateAssociationContext` at `0x1800028b8`

## pseudocode

```c
__int64 load_DafCreateAssociationContext()
{
  return _tailMerge_deviceassociation_dll();
}

```

## disassembly

```asm
0x1800028b8  lea     rax, __imp_DafCreateAssociationContext
0x1800028bf  jmp     __tailMerge_deviceassociation_dll
```
