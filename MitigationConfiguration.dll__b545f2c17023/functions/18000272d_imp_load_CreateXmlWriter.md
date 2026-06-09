# __imp_load_CreateXmlWriter

- ea: `0x18000272d`
- end: `0x180002739`
- name: `__imp_load_CreateXmlWriter`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800026ae`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18000272d`

## pseudocode

```c
__int64 load_CreateXmlWriter()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x18000272d  lea     rax, __imp_CreateXmlWriter
0x180002734  jmp     __tailMerge_xmllite_dll
```
