# Namespace::WriteDecl

- ea: `0x1106d0`
- end: `0x110733`
- name: `Namespace::WriteDecl`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x3e6e0`

## callees

- `0x211a0`
- `0x40840`
- `0x40860`
- `0x408d0`
- `0x1106d0`

## string_xrefs

- `0x1106fe`: `http://www.w3.org/2000/xmlns/`
- `0x110716`: `http://www.w3.org/2000/xmlns/`
- `0x1106f9`: `xmlns`
- `0x11070b`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x1106d0  ldarg.2
0x1106d1  brfalse.s loc_1106E6
0x1106d3  ldarg.2
0x1106d4  ldarg.0
0x1106d5  ldfld    string Namespace::prefix
0x1106da  ldarg.0
0x1106db  ldfld    string Namespace::namespaceUri
0x1106e0  callvirt instance void System.Xml.XmlRawWriter::WriteNamespaceDeclaration(string prefix, string ns)
0x1106e5  ret
0x1106e6  ldarg.0
0x1106e7  ldfld    string Namespace::prefix
0x1106ec  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1106f1  brtrue.s loc_11070A
0x1106f3  ldarg.1
0x1106f4  ldsfld   string [mscorlib]System.String::Empty
0x1106f9  ldstr    aXmlns// "xmlns"
0x1106fe  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x110703  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0x110708  br.s     loc_110720
0x11070a  ldarg.1
0x11070b  ldstr    aXmlns// "xmlns"
0x110710  ldarg.0
0x110711  ldfld    string Namespace::prefix
0x110716  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x11071b  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0x110720  ldarg.1
0x110721  ldarg.0
0x110722  ldfld    string Namespace::namespaceUri
0x110727  callvirt instance void System.Xml.XmlWriter::WriteString(string text)
0x11072c  ldarg.1
0x11072d  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0x110732  ret
```
