# Microsoft.ReportingServices.Modeling.ModelGeneration.CreateVariationAttributeRule::LoadXmlElement

- ea: `0x27190`
- end: `0x271d0`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.CreateVariationAttributeRule::LoadXmlElement`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa7b0`
- `0xa7c0`
- `0xae90`
- `0x27190`
- `0x29f80`

## string_xrefs

- `0x27196`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x27190  ldarg.1
0x27191  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x27196  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x2719b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x271a0  brfalse.s loc_271C7
0x271a2  ldarg.1
0x271a3  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x271a8  ldstr    aAttribute// "Attribute"
0x271ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x271b2  brfalse.s loc_271C7
0x271b4  ldarg.0
0x271b5  ldfld    class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class [System.Xml]System.Xml.XPath.IXPathNavigable> Microsoft.ReportingServices.Modeling.ModelGeneration.CreateVariationAttributeRule::m_attributeFragments
0x271ba  ldarg.1
0x271bb  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x271c0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XPath.IXPathNavigable>::Add(var<u1>)
0x271c5  ldc.i4.1
0x271c6  ret
0x271c7  ldarg.0
0x271c8  ldarg.1
0x271c9  ldarg.2
0x271ca  call     instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr, class Microsoft.ReportingServices.Modeling.ModelGeneration.IXmlObjectFactory objectFactory)
0x271cf  ret
```
