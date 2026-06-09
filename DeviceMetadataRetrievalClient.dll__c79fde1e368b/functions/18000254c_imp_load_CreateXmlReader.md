# __imp_load_CreateXmlReader

- ea: `0x18000254c`
- end: `0x180002558`
- name: `__imp_load_CreateXmlReader`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800024cd`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18000254c`

## pseudocode

```c
__int64 load_CreateXmlReader()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x18000254c  lea     rax, __imp_CreateXmlReader
0x180002553  jmp     __tailMerge_xmllite_dll
```
