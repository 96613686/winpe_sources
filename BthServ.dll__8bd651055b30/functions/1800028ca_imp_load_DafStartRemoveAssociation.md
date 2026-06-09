# __imp_load_DafStartRemoveAssociation

- ea: `0x1800028ca`
- end: `0x1800028d6`
- name: `__imp_load_DafStartRemoveAssociation`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002839`

## import_xrefs

- `deviceassociation!DafStartRemoveAssociation` at `0x1800028ca`

## pseudocode

```c
__int64 load_DafStartRemoveAssociation()
{
  return _tailMerge_deviceassociation_dll();
}

```

## disassembly

```asm
0x1800028ca  lea     rax, __imp_DafStartRemoveAssociation
0x1800028d1  jmp     __tailMerge_deviceassociation_dll
```
