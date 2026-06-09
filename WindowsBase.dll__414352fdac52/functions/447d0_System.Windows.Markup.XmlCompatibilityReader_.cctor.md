# System.Windows.Markup.XmlCompatibilityReader::.cctor

- ea: `0x447d0`
- end: `0x447fc`
- name: `System.Windows.Markup.XmlCompatibilityReader::.cctor`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x447e8`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x447f0`: `http://schemas.openxmlformats.org/markup-compatibility/2006`
- `0x447d8`: `http://www.w3.org/2000/xmlns/`
- `0x447e0`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x447d0  ldc.i4.4
0x447d1  newarr   [mscorlib]System.String
0x447d6  dup
0x447d7  ldc.i4.0
0x447d8  ldstr    aHttpWwwW3Org20_7// "http://www.w3.org/2000/xmlns/"
0x447dd  stelem.ref
0x447de  dup
0x447df  ldc.i4.1
0x447e0  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x447e5  stelem.ref
0x447e6  dup
0x447e7  ldc.i4.2
0x447e8  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2001/XMLSchema-instan"...
0x447ed  stelem.ref
0x447ee  dup
0x447ef  ldc.i4.3
0x447f0  ldstr    aHttpSchemasOpe_5// "http://schemas.openxmlformats.org/marku"...
0x447f5  stelem.ref
0x447f6  stsfld   string[] System.Windows.Markup.XmlCompatibilityReader::_predefinedNamespaces
0x447fb  ret
```
