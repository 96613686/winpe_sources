# __imp_load_FveAuthElementReadExternalKeyW

- ea: `0x180003101`
- end: `0x18000310d`
- name: `__imp_load_FveAuthElementReadExternalKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003082`

## import_xrefs

- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x180003101`

## pseudocode

```c
__int64 load_FveAuthElementReadExternalKeyW()
{
  return _tailMerge_fveapi_dll();
}

```

## disassembly

```asm
0x180003101  lea     rax, __imp_FveAuthElementReadExternalKeyW
0x180003108  jmp     __tailMerge_fveapi_dll
```
