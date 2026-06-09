# System.Xml.XPath.XPathNavigator::CheckValidity

- ea: `0xef660`
- end: `0xef77b`
- name: `System.Xml.XPath.XPathNavigator::CheckValidity`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x21c60`
- `0x622f0`
- `0x62370`
- `0xbd560`
- `0xbd570`
- `0xbd580`
- `0xcba10`
- `0xeefc0`
- `0xef650`
- `0xef660`
- `0xef780`
- `0xf0360`
- `0x126760`
- `0x1267e0`

## string_xrefs

- `0xef689`: `XPathDocument_MissingSchemas`
- `0xef6a3`: `XPathDocument_MissingSchemas`
- `0xef6e5`: `XPathDocument_MissingSchemas`
- `0xef6d1`: `XPathDocument_NotEnoughSchemaInfo`
- `0xef713`: `XPathDocument_NotEnoughSchemaInfo`
- `0xef724`: `XPathDocument_ValidateInvalidNodeType`

## pseudocode

```c

```

## disassembly

```asm
0xef660  ldnull
0xef661  stloc.1
0xef662  ldnull
0xef663  stloc.2
0xef664  ldnull
0xef665  stloc.3
0xef666  ldarg.0
0xef667  callvirt instance valuetype System.Xml.XPath.XPathNodeType System.Xml.XPath.XPathNavigator::get_NodeType()
0xef66c  stloc.s  7
0xef66e  ldloc.s  7
0xef670  switch   loc_EF686, loc_EF6A0, loc_EF6E2
0xef681  br       loc_EF724
0xef686  ldarg.1
0xef687  brtrue.s loc_EF699
0xef689  ldstr    aXpathdocumentM// "XPathDocument_MissingSchemas"
0xef68e  call     string System.Xml.Res::GetString(string name)
0xef693  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xef698  throw
0xef699  ldnull
0xef69a  stloc.1
0xef69b  br       loc_EF735
0xef6a0  ldarg.1
0xef6a1  brtrue.s loc_EF6B3
0xef6a3  ldstr    aXpathdocumentM// "XPathDocument_MissingSchemas"
0xef6a8  call     string System.Xml.Res::GetString(string name)
0xef6ad  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xef6b2  throw
0xef6b3  ldarg.0
0xef6b4  callvirt instance class System.Xml.Schema.IXmlSchemaInfo System.Xml.XPath.XPathNavigator::get_SchemaInfo()
0xef6b9  stloc.0
0xef6ba  ldloc.0
0xef6bb  brfalse.s loc_EF6CB
0xef6bd  ldloc.0
0xef6be  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.IXmlSchemaInfo::get_SchemaType()
0xef6c3  stloc.1
0xef6c4  ldloc.0
0xef6c5  callvirt instance class System.Xml.Schema.XmlSchemaElement System.Xml.Schema.IXmlSchemaInfo::get_SchemaElement()
0xef6ca  stloc.2
0xef6cb  ldloc.1
0xef6cc  brtrue.s loc_EF735
0xef6ce  ldloc.2
0xef6cf  brtrue.s loc_EF735
0xef6d1  ldstr    aXpathdocumentN// "XPathDocument_NotEnoughSchemaInfo"
0xef6d6  ldnull
0xef6d7  call     string System.Xml.Res::GetString(string name, object[] args)
0xef6dc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xef6e1  throw
0xef6e2  ldarg.1
0xef6e3  brtrue.s loc_EF6F5
0xef6e5  ldstr    aXpathdocumentM// "XPathDocument_MissingSchemas"
0xef6ea  call     string System.Xml.Res::GetString(string name)
0xef6ef  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xef6f4  throw
0xef6f5  ldarg.0
0xef6f6  callvirt instance class System.Xml.Schema.IXmlSchemaInfo System.Xml.XPath.XPathNavigator::get_SchemaInfo()
0xef6fb  stloc.0
0xef6fc  ldloc.0
0xef6fd  brfalse.s loc_EF70D
0xef6ff  ldloc.0
0xef700  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.IXmlSchemaInfo::get_SchemaType()
0xef705  stloc.1
0xef706  ldloc.0
0xef707  callvirt instance class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.IXmlSchemaInfo::get_SchemaAttribute()
0xef70c  stloc.3
0xef70d  ldloc.1
0xef70e  brtrue.s loc_EF735
0xef710  ldloc.3
0xef711  brtrue.s loc_EF735
0xef713  ldstr    aXpathdocumentN// "XPathDocument_NotEnoughSchemaInfo"
0xef718  ldnull
0xef719  call     string System.Xml.Res::GetString(string name, object[] args)
0xef71e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xef723  throw
0xef724  ldstr    aXpathdocumentV// "XPathDocument_ValidateInvalidNodeType"
0xef729  ldnull
0xef72a  call     string System.Xml.Res::GetString(string name, object[] args)
0xef72f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xef734  throw
0xef735  ldarg.0
0xef736  call     instance class System.Xml.XmlReader System.Xml.XPath.XPathNavigator::CreateReader()
0xef73b  stloc.s  4
0xef73d  ldarg.2
0xef73e  ldloc.s  4
0xef740  isinst   System.Xml.XPath.XPathNavigatorReader
0xef745  newobj   instance void CheckValidityHelper::.ctor(class System.Xml.Schema.ValidationEventHandler nextEventHandler, class System.Xml.XPath.XPathNavigatorReader reader)
0xef74a  stloc.s  5
0xef74c  ldloc.s  5
0xef74e  ldftn    instance void CheckValidityHelper::ValidationCallback(object sender, class System.Xml.Schema.ValidationEventArgs args)
0xef754  newobj   instance void System.Xml.Schema.ValidationEventHandler::.ctor(object object, native int method)
0xef759  starg.s  2
0xef75b  ldarg.0
0xef75c  ldloc.s  4
0xef75e  ldarg.1
0xef75f  ldarg.2
0xef760  ldloc.1
0xef761  ldloc.2
0xef762  ldloc.3
0xef763  call     instance class System.Xml.XmlReader System.Xml.XPath.XPathNavigator::GetValidatingReader(class System.Xml.XmlReader reader, class System.Xml.Schema.XmlSchemaSet schemas, class System.Xml.Schema.ValidationEventHandler validationEvent, class System.Xml.Schema.XmlSchemaType schemaType, class System.Xml.Schema.XmlSchemaElement schemaElement, class System.Xml.Schema.XmlSchemaAttribute schemaAttribute)
0xef768  stloc.s  6
0xef76a  ldloc.s  6
0xef76c  callvirt instance bool System.Xml.XmlReader::Read()
0xef771  brtrue.s loc_EF76A
0xef773  ldloc.s  5
0xef775  callvirt instance bool CheckValidityHelper::get_IsValid()
0xef77a  ret
```
