# System.Xml.Xsl.Runtime.XmlQueryRuntime::ParseTagName_1

- ea: `0x30cf0`
- end: `0x30d94`
- name: `System.Xml.Xsl.Runtime.XmlQueryRuntime::ParseTagName_1`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x30570`
- `0x30cb0`

## callees

- `0x380`
- `0x390`
- `0x3780`
- `0x30cf0`

## string_xrefs

- `0x30d68`: `xmlns`
- `0x30d76`: `http://www.w3.org/2000/xmlns/`
- `0x30d5f`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x30cf0  ldarg.1
0x30cf1  ldarg.3
0x30cf2  ldarg.s  4
0x30cf4  call     void [System.Xml]System.Xml.ValidateNames::ParseQNameThrow(string, string&, string&)
0x30cf9  ldarg.s  5
0x30cfb  ldnull
0x30cfc  stind.ref
0x30cfd  ldarg.0
0x30cfe  ldfld    valuetype System.Xml.Xsl.StringPair[][] System.Xml.Xsl.Runtime.XmlQueryRuntime::prefixMappingsList
0x30d03  ldarg.2
0x30d04  ldelem.ref
0x30d05  stloc.0
0x30d06  ldc.i4.0
0x30d07  stloc.1
0x30d08  br.s     loc_30D32
0x30d0a  ldloc.0
0x30d0b  ldloc.1
0x30d0c  ldelem   System.Xml.Xsl.StringPair
0x30d11  stloc.2
0x30d12  ldarg.3
0x30d13  ldind.ref
0x30d14  ldloca.s 2
0x30d16  call     instance string System.Xml.Xsl.StringPair::get_Left()
0x30d1b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x30d20  brfalse.s loc_30D2E
0x30d22  ldarg.s  5
0x30d24  ldloca.s 2
0x30d26  call     instance string System.Xml.Xsl.StringPair::get_Right()
0x30d2b  stind.ref
0x30d2c  br.s     loc_30D38
0x30d2e  ldloc.1
0x30d2f  ldc.i4.1
0x30d30  add
0x30d31  stloc.1
0x30d32  ldloc.1
0x30d33  ldloc.0
0x30d34  ldlen
0x30d35  conv.i4
0x30d36  blt.s    loc_30D0A
0x30d38  ldarg.s  5
0x30d3a  ldind.ref
0x30d3b  brtrue.s loc_30D93
0x30d3d  ldarg.3
0x30d3e  ldind.ref
0x30d3f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x30d44  brtrue.s loc_30D4F
0x30d46  ldarg.s  5
0x30d48  ldstr    asc_580D4// ""
0x30d4d  stind.ref
0x30d4e  ret
0x30d4f  ldarg.3
0x30d50  ldind.ref
0x30d51  ldstr    aXml// "xml"
0x30d56  callvirt instance bool [mscorlib]System.String::Equals(string)
0x30d5b  brfalse.s loc_30D66
0x30d5d  ldarg.s  5
0x30d5f  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x30d64  stind.ref
0x30d65  ret
0x30d66  ldarg.3
0x30d67  ldind.ref
0x30d68  ldstr    aXmlns// "xmlns"
0x30d6d  callvirt instance bool [mscorlib]System.String::Equals(string)
0x30d72  brfalse.s loc_30D7D
0x30d74  ldarg.s  5
0x30d76  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x30d7b  stind.ref
0x30d7c  ret
0x30d7d  ldstr    aXsltInvalidpre// "Xslt_InvalidPrefix"
0x30d82  ldc.i4.1
0x30d83  newarr   [mscorlib]System.String
0x30d88  dup
0x30d89  ldc.i4.0
0x30d8a  ldarg.3
0x30d8b  ldind.ref
0x30d8c  stelem.ref
0x30d8d  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x30d92  throw
0x30d93  ret
```
