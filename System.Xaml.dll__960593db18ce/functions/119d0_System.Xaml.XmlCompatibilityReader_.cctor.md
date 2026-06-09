# System.Xaml.XmlCompatibilityReader::.cctor

- ea: `0x119d0`
- end: `0x119fc`
- name: `System.Xaml.XmlCompatibilityReader::.cctor`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x119e0`: `http://www.w3.org/XML/1998/namespace`
- `0x119f0`: `http://schemas.openxmlformats.org/markup-compatibility/2006`
- `0x119d8`: `http://www.w3.org/2000/xmlns/`
- `0x119e8`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0x119d0  ldc.i4.4
0x119d1  newarr   [mscorlib]System.String
0x119d6  dup
0x119d7  ldc.i4.0
0x119d8  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x119dd  stelem.ref
0x119de  dup
0x119df  ldc.i4.1
0x119e0  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x119e5  stelem.ref
0x119e6  dup
0x119e7  ldc.i4.2
0x119e8  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema-instan"...
0x119ed  stelem.ref
0x119ee  dup
0x119ef  ldc.i4.3
0x119f0  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/marku"...
0x119f5  stelem.ref
0x119f6  stsfld   string[] System.Xaml.XmlCompatibilityReader::_predefinedNamespaces
0x119fb  ret
```
