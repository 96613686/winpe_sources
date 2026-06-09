# __imp_load_DafCreateAssociationContextFromOobBlob

- ea: `0x1800028ee`
- end: `0x1800028fa`
- name: `__imp_load_DafCreateAssociationContextFromOobBlob`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002839`

## import_xrefs

- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x1800028ee`

## pseudocode

```c
__int64 load_DafCreateAssociationContextFromOobBlob()
{
  return _tailMerge_deviceassociation_dll();
}

```

## disassembly

```asm
0x1800028ee  lea     rax, __imp_DafCreateAssociationContextFromOobBlob
0x1800028f5  jmp     __tailMerge_deviceassociation_dll
```
