# Microsoft.ReportingServices.Modeling.DrillthroughContext::LoadCore

- ea: `0x17fc0`
- end: `0x1802d`
- name: `Microsoft.ReportingServices.Modeling.DrillthroughContext::LoadCore`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x35f90`

## callees

- `0xa730`
- `0xa750`
- `0xab20`
- `0xbaa0`
- `0x17fc0`
- `0x23440`
- `0x25a60`
- `0x25bb0`
- `0x25be0`

## string_xrefs

- `0x18002`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x17fc0  ldarg.0
0x17fc1  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.DrillthroughContext::m_sourceQuery
0x17fc6  ldarg.1
0x17fc7  callvirt instance void Microsoft.ReportingServices.Modeling.SemanticQuery::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x17fcc  ldarg.1
0x17fcd  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x17fd2  callvirt instance bool Microsoft.ReportingServices.Modeling.ValidationContext::get_HasErrors()
0x17fd7  brfalse.s loc_17FDA
0x17fd9  ret
0x17fda  ldarg.2
0x17fdb  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x17fe0  ldarg.0
0x17fe1  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.DrillthroughContext::m_sourceQuery
0x17fe6  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x17feb  ldarg.2
0x17fec  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x17ff1  ldarg.0
0x17ff2  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x17ff7  ldarg.2
0x17ff8  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Reader()
0x17ffd  ldstr    aDrillthroughco// "DrillthroughContext"
0x18002  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x18007  call     void Microsoft.ReportingServices.Modeling.XmlUtil::CheckElement(class [System.Xml]System.Xml.XmlReader xr, string localName, string namespaceUri)
0x1800c  ldarg.2
0x1800d  ldarg.0
0x1800e  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject(class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0x18013  leave.s  loc_1802C
0x18015  ldarg.2
0x18016  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x1801b  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x18020  ldarg.2
0x18021  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x18026  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x1802b  endfinally
0x1802c  ret
```
