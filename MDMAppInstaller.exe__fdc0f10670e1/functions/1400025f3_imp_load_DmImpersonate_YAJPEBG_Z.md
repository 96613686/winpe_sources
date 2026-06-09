# __imp_load_?DmImpersonate@@YAJPEBG@Z

- ea: `0x1400025f3`
- end: `0x1400025ff`
- name: `__imp_load_?DmImpersonate@@YAJPEBG@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140002550`

## import_xrefs

- `DMCmnUtils!DmImpersonate` at `0x1400025f3`

## pseudocode

```c
__int64 load__DmImpersonate__YAJPEBG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x1400025f3  lea     rax, __imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1400025fa  jmp     __tailMerge_dmcmnutils_dll
```
