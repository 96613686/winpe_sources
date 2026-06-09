# __imp_load_SamRidToSid

- ea: `0x180010293`
- end: `0x18001029f`
- name: `__imp_load_SamRidToSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180010184`

## import_xrefs

- `SAMLIB!SamRidToSid` at `0x180010293`

## pseudocode

```c
__int64 load_SamRidToSid()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x180010293  lea     rax, __imp_SamRidToSid
0x18001029a  jmp     __tailMerge_samlib_dll
```
