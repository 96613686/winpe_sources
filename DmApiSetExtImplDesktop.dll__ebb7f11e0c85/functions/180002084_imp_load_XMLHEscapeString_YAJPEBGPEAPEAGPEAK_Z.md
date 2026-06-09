# __imp_load_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z

- ea: `0x180002084`
- end: `0x180002090`
- name: `__imp_load_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002005`

## import_xrefs

- `dmxmlhelputils!XMLHEscapeString` at `0x180002084`

## pseudocode

```c
__int64 load__XMLHEscapeString__YAJPEBGPEAPEAGPEAK_Z()
{
  return _tailMerge_dmxmlhelputils_dll();
}

```

## disassembly

```asm
0x180002084  lea     rax, __imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x18000208b  jmp     __tailMerge_dmxmlhelputils_dll
```
