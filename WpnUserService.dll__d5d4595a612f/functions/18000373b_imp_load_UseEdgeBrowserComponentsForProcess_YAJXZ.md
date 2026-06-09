# __imp_load_?UseEdgeBrowserComponentsForProcess@@YAJXZ

- ea: `0x18000373b`
- end: `0x180003747`
- name: `__imp_load_?UseEdgeBrowserComponentsForProcess@@YAJXZ`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800036bc`

## import_xrefs

- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18000373b`

## pseudocode

```c
__int64 load__UseEdgeBrowserComponentsForProcess__YAJXZ()
{
  return _tailMerge_iertutil_dll();
}

```

## disassembly

```asm
0x18000373b  lea     rax, __imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ; UseEdgeBrowserComponentsForProcess(void)
0x180003742  jmp     __tailMerge_iertutil_dll
```
