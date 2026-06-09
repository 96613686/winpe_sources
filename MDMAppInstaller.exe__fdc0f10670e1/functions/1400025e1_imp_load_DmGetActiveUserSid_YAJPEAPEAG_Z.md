# __imp_load_?DmGetActiveUserSid@@YAJPEAPEAG@Z

- ea: `0x1400025e1`
- end: `0x1400025ed`
- name: `__imp_load_?DmGetActiveUserSid@@YAJPEAPEAG@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140002550`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x1400025e1`

## pseudocode

```c
__int64 load__DmGetActiveUserSid__YAJPEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x1400025e1  lea     rax, __imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1400025e8  jmp     __tailMerge_dmcmnutils_dll
```
