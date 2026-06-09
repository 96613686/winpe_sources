# __imp_load_CreateXmlReader

- ea: `0x180001f6a`
- end: `0x180001f76`
- name: `__imp_load_CreateXmlReader`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001eeb`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180001f6a`

## pseudocode

```c
__int64 load_CreateXmlReader()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180001f6a  lea     rax, __imp_CreateXmlReader
0x180001f71  jmp     __tailMerge_xmllite_dll
```
