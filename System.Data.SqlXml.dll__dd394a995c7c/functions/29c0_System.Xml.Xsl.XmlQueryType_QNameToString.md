# System.Xml.Xsl.XmlQueryType::QNameToString

- ea: `0x29c0`
- end: `0x2a44`
- name: `System.Xml.Xsl.XmlQueryType::QNameToString`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x2820`
- `0x28f0`

## callees

- `0x29c0`

## string_xrefs

- `0x29e8`: `http://www.w3.org/2001/XMLSchema`
- `0x2a0b`: `http://www.w3.org/2003/11/xpath-datatypes`

## pseudocode

```c

```

## disassembly

```asm
0x29c0  ldarg.0
0x29c1  callvirt instance bool [System.Xml]System.Xml.XmlQualifiedName::get_IsEmpty()
0x29c6  brfalse.s loc_29CE
0x29c8  ldstr    asc_580B6// "*"
0x29cd  ret
0x29ce  ldarg.0
0x29cf  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x29d4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29d9  brtrue.s loc_29E2
0x29db  ldarg.0
0x29dc  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x29e1  ret
0x29e2  ldarg.0
0x29e3  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x29e8  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x29ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29f2  brfalse.s loc_2A05
0x29f4  ldstr    aXs// "xs:"
0x29f9  ldarg.0
0x29fa  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x29ff  call     string [mscorlib]System.String::Concat(string, string)
0x2a04  ret
0x2a05  ldarg.0
0x2a06  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x2a0b  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2003/11/xpath-datatyp"...
0x2a10  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a15  brfalse.s loc_2A28
0x2a17  ldstr    aXdt// "xdt:"
0x2a1c  ldarg.0
0x2a1d  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x2a22  call     string [mscorlib]System.String::Concat(string, string)
0x2a27  ret
0x2a28  ldstr    asc_580CC// "{"
0x2a2d  ldarg.0
0x2a2e  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x2a33  ldstr    asc_587DE// "}"
0x2a38  ldarg.0
0x2a39  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x2a3e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2a43  ret
```
