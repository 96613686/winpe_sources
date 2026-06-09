# Microsoft.ReportingServices.Modeling.ModelGeneration.EntityRuleBase::LoadXmlElement

- ea: `0x27560`
- end: `0x275ba`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.EntityRuleBase::LoadXmlElement`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa7b0`
- `0xa7c0`
- `0xae90`
- `0x27560`
- `0x29f80`

## string_xrefs

- `0x27566`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x27560  ldarg.1
0x27561  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x27566  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x2756b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27570  brfalse.s loc_275B1
0x27572  ldarg.1
0x27573  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x27578  stloc.0
0x27579  ldloc.0
0x2757a  ldstr    aEntity// "Entity"
0x2757f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27584  brtrue.s loc_27595
0x27586  ldloc.0
0x27587  ldstr    aEntityfolder// "EntityFolder"
0x2758c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27591  brtrue.s loc_275A3
0x27593  br.s     loc_275B1
0x27595  ldarg.0
0x27596  ldarg.1
0x27597  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x2759c  stfld    class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.EntityRuleBase::m_entityFragment
0x275a1  ldc.i4.1
0x275a2  ret
0x275a3  ldarg.0
0x275a4  ldarg.1
0x275a5  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x275aa  stfld    class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.EntityRuleBase::m_folderFragment
0x275af  ldc.i4.1
0x275b0  ret
0x275b1  ldarg.0
0x275b2  ldarg.1
0x275b3  ldarg.2
0x275b4  call     instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr, class Microsoft.ReportingServices.Modeling.ModelGeneration.IXmlObjectFactory objectFactory)
0x275b9  ret
```
