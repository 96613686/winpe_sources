# __imp_load_?UseEdgeBrowserComponentsForProcess@@YAJXZ

- ea: `0x18000272d`
- end: `0x180002739`
- name: `__imp_load_?UseEdgeBrowserComponentsForProcess@@YAJXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026ae`

## import_xrefs

- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18000272d`

## pseudocode

```c
__int64 load__UseEdgeBrowserComponentsForProcess__YAJXZ()
{
  return _tailMerge_iertutil_dll();
}

```

## disassembly

```asm
0x18000272d  lea     rax, __imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ; UseEdgeBrowserComponentsForProcess(void)
0x180002734  jmp     __tailMerge_iertutil_dll
```
