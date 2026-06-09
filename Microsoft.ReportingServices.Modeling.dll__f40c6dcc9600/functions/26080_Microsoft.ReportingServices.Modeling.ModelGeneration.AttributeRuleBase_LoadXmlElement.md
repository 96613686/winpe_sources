# Microsoft.ReportingServices.Modeling.ModelGeneration.AttributeRuleBase::LoadXmlElement

- ea: `0x26080`
- end: `0x260da`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.AttributeRuleBase::LoadXmlElement`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa7b0`
- `0xa7c0`
- `0xae90`
- `0x26080`
- `0x29f80`

## string_xrefs

- `0x26086`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x26080  ldarg.1
0x26081  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x26086  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x2608b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26090  brfalse.s loc_260D1
0x26092  ldarg.1
0x26093  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x26098  stloc.0
0x26099  ldloc.0
0x2609a  ldstr    aAttribute// "Attribute"
0x2609f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x260a4  brtrue.s loc_260B5
0x260a6  ldloc.0
0x260a7  ldstr    aFieldfolder// "FieldFolder"
0x260ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x260b1  brtrue.s loc_260C3
0x260b3  br.s     loc_260D1
0x260b5  ldarg.0
0x260b6  ldarg.1
0x260b7  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x260bc  stfld    class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.AttributeRuleBase::m_attributeFragment
0x260c1  ldc.i4.1
0x260c2  ret
0x260c3  ldarg.0
0x260c4  ldarg.1
0x260c5  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x260ca  stfld    class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.AttributeRuleBase::m_folderFragment
0x260cf  ldc.i4.1
0x260d0  ret
0x260d1  ldarg.0
0x260d2  ldarg.1
0x260d3  ldarg.2
0x260d4  call     instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr, class Microsoft.ReportingServices.Modeling.ModelGeneration.IXmlObjectFactory objectFactory)
0x260d9  ret
```
