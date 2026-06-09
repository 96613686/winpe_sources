# System.Xml.Xsl.XmlQueryType::get_IsSingleton

- ea: `0x2370`
- end: `0x2381`
- name: `System.Xml.Xsl.XmlQueryType::get_IsSingleton`
- size: `17`
- prototype: ``
- caller_count: `53`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18290`
- `0x1aee0`
- `0x1b310`
- `0x1b960`
- `0x1bba0`
- `0x27280`
- `0x27310`
- `0x28030`
- `0x28080`
- `0x281a0`
- `0x29a90`
- `0x29b80`
- `0x2f390`
- `0x31010`
- `0x37ff0`
- `0x41ab0`
- `0x41c00`
- `0x42fa0`
- `0x43020`
- `0x43650`
- `0x44900`
- `0x44b30`
- `0x44e60`
- `0x46190`
- `0x47070`
- `0x4a2a0`
- `0x4a9f0`
- `0x4aa60`
- `0x4ad40`
- `0x4b030`
- `0x4b810`
- `0x4bdc0`
- `0x4c070`
- `0x4c5b0`
- `0x4d200`
- `0x4d420`
- `0x4d740`
- `0x4d8a0`
- `0x4dc70`
- `0x4e720`
- `0x4e7a0`
- `0x4e900`
- `0x4ece0`
- `0x4ee70`
- `0x4f110`
- `0x4f610`
- `0x4faf0`
- `0x50210`
- `0x50270`
- `0x505b0`

## callees

- `0x1350`
- `0x14a0`
- `0x1fe0`

## pseudocode

```c

```

## disassembly

```asm
0x2370  ldarg.0
0x2371  callvirt instance valuetype System.Xml.Xsl.XmlQueryCardinality System.Xml.Xsl.XmlQueryType::get_Cardinality()
0x2376  call     valuetype System.Xml.Xsl.XmlQueryCardinality System.Xml.Xsl.XmlQueryCardinality::get_One()
0x237b  call     bool System.Xml.Xsl.XmlQueryCardinality::op_LessThanOrEqual(valuetype System.Xml.Xsl.XmlQueryCardinality left, valuetype System.Xml.Xsl.XmlQueryCardinality right)
0x2380  ret
```
