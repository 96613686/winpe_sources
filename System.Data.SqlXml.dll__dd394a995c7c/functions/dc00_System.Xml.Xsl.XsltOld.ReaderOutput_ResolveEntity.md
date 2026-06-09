# System.Xml.Xsl.XsltOld.ReaderOutput::ResolveEntity

- ea: `0xdc00`
- end: `0xdc1a`
- name: `System.Xml.Xsl.XsltOld.ReaderOutput::ResolveEntity`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x230`
- `0xdc00`

## string_xrefs

- `0xdc09`: `Xml_InvalidOperation`

## pseudocode

```c

```

## disassembly

```asm
0xdc00  ldarg.0
0xdc01  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xdc06  ldc.i4.5
0xdc07  beq.s    loc_DC19
0xdc09  ldstr    aXmlInvalidoper// "Xml_InvalidOperation"
0xdc0e  call     string System.Xml.Utils.Res::GetString(string name)
0xdc13  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xdc18  throw
0xdc19  ret
```
