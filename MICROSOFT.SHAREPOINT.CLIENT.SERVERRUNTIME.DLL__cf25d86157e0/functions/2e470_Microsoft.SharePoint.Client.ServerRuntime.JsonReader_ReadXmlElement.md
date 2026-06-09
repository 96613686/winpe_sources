# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadXmlElement

- ea: `0x2e470`
- end: `0x2e51c`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadXmlElement`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e3f0`
- `0x2e420`
- `0x2e580`

## callees

- `0x16f10`
- `0x2d6f0`
- `0x2d930`
- `0x2d970`
- `0x2d9f0`
- `0x2e470`
- `0x2e520`
- `0x2e580`
- `0x2eb00`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2e4de`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2e470  ldarg.0
0x2e471  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectStart()
0x2e476  br.s     loc_2E47F
0x2e478  ldarg.0
0x2e479  call     instance string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadString()
0x2e47e  pop
0x2e47f  ldarg.0
0x2e480  call     instance string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadName()
0x2e485  ldstr    aName// "Name"
0x2e48a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2e48f  brtrue.s loc_2E478
0x2e491  ldarg.0
0x2e492  call     instance string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadString()
0x2e497  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x2e49c  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName)
0x2e4a1  stloc.0
0x2e4a2  ldarg.1
0x2e4a3  ldloc.0
0x2e4a4  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x2e4a9  br.s     loc_2E504
0x2e4ab  ldarg.0
0x2e4ac  call     instance string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadName()
0x2e4b1  stloc.2
0x2e4b2  ldloc.2
0x2e4b3  ldstr    aAttributes// "Attributes"
0x2e4b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4bd  brfalse.s loc_2E4C8
0x2e4bf  ldarg.0
0x2e4c0  ldloc.0
0x2e4c1  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadXmlAttributes(class [System.Xml.Linq]System.Xml.Linq.XElement elem)
0x2e4c6  br.s     loc_2E504
0x2e4c8  ldloc.2
0x2e4c9  ldstr    aChildren// "Children"
0x2e4ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4d3  brfalse.s loc_2E4DE
0x2e4d5  ldarg.0
0x2e4d6  ldloc.0
0x2e4d7  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadXmlChildren(class [System.Xml.Linq]System.Xml.Linq.XElement parent)
0x2e4dc  br.s     loc_2E504
0x2e4de  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2e4e3  ldc.i4.1
0x2e4e4  newarr   [mscorlib]System.Object
0x2e4e9  stloc.3
0x2e4ea  ldloc.3
0x2e4eb  ldc.i4.0
0x2e4ec  ldloc.1
0x2e4ed  callvirt instance int32 Token::get_Position()
0x2e4f2  box      [mscorlib]System.Int32
0x2e4f7  stelem.ref
0x2e4f8  ldloc.3
0x2e4f9  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2e4fe  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e503  throw
0x2e504  ldarg.0
0x2e505  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2e50a  dup
0x2e50b  stloc.1
0x2e50c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e511  ldc.i4.1
0x2e512  bne.un.s loc_2E4AB
0x2e514  ldarg.0
0x2e515  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectEnd()
0x2e51a  ldloc.0
0x2e51b  ret
```
