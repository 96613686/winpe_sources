# __imp_load_CreateXmlReader

- ea: `0x18000273f`
- end: `0x18000274b`
- name: `__imp_load_CreateXmlReader`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800026ae`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18000273f`

## pseudocode

```c
__int64 load_CreateXmlReader()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x18000273f  lea     rax, __imp_CreateXmlReader
0x180002746  jmp     __tailMerge_xmllite_dll
```
