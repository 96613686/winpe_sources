# Microsoft.ReportingServices.Modeling.SemanticModelingSchema::AddXmlSchemas

- ea: `0xa4e0`
- end: `0xa592`
- name: `Microsoft.ReportingServices.Modeling.SemanticModelingSchema::AddXmlSchemas`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`
- `0xa3b0`
- `0xa3f0`
- `0xa4e0`

## string_xrefs

- `0xa55a`: `allowReplacementTokens`

## pseudocode

```c

```

## disassembly

```asm
0xa4e0  ldarg.1
0xa4e1  ldstr    aSchemaDatasour// "Schema.DataSourceView.xsd"
0xa4e6  call     class [System.Xml]System.Xml.Schema.XmlSchema Microsoft.ReportingServices.Modeling.ModelingXmlSchema::ReadXmlSchema(string schemaName)
0xa4eb  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0xa4f0  pop
0xa4f1  ldarg.0
0xa4f2  ldsfld   class Microsoft.ReportingServices.Modeling.SemanticModelingSchema Microsoft.ReportingServices.Modeling.SemanticModelingSchema::m_strictInstance
0xa4f7  bne.un.s loc_A50B
0xa4f9  ldarg.1
0xa4fa  ldstr    aSchemaSemantic// "Schema.SemanticModeling.xsd"
0xa4ff  call     class [System.Xml]System.Xml.Schema.XmlSchema Microsoft.ReportingServices.Modeling.ModelingXmlSchema::ReadXmlSchema(string schemaName)
0xa504  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0xa509  pop
0xa50a  ret
0xa50b  ldarg.0
0xa50c  ldsfld   class Microsoft.ReportingServices.Modeling.SemanticModelingSchema Microsoft.ReportingServices.Modeling.SemanticModelingSchema::m_relaxedInstance
0xa511  bne.un.s loc_A52B
0xa513  ldarg.1
0xa514  ldstr    aSchemaSemantic// "Schema.SemanticModeling.xsd"
0xa519  ldstr    aSchemaSemantic_0// "Schema.SemanticModelingRelaxed.xslt"
0xa51e  ldnull
0xa51f  call     class [System.Xml]System.Xml.Schema.XmlSchema Microsoft.ReportingServices.Modeling.ModelingXmlSchema::ReadXmlSchemaWithTransform(string schemaName, string transformName, class [System.Xml]System.Xml.Xsl.XsltArgumentList arguments)
0xa524  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0xa529  pop
0xa52a  ret
0xa52b  ldarg.0
0xa52c  ldsfld   class Microsoft.ReportingServices.Modeling.SemanticModelingSchema Microsoft.ReportingServices.Modeling.SemanticModelingSchema::m_fragmentInstance
0xa531  bne.un.s loc_A54B
0xa533  ldarg.1
0xa534  ldstr    aSchemaSemantic// "Schema.SemanticModeling.xsd"
0xa539  ldstr    aSchemaSemantic_1// "Schema.SemanticModelingFragment.xslt"
0xa53e  ldnull
0xa53f  call     class [System.Xml]System.Xml.Schema.XmlSchema Microsoft.ReportingServices.Modeling.ModelingXmlSchema::ReadXmlSchemaWithTransform(string schemaName, string transformName, class [System.Xml]System.Xml.Xsl.XsltArgumentList arguments)
0xa544  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0xa549  pop
0xa54a  ret
0xa54b  ldarg.0
0xa54c  ldsfld   class Microsoft.ReportingServices.Modeling.SemanticModelingSchema Microsoft.ReportingServices.Modeling.SemanticModelingSchema::m_fragmentWithReplacementsInstance
0xa551  bne.un.s loc_A587
0xa553  newobj   instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::.ctor()
0xa558  stloc.0
0xa559  ldloc.0
0xa55a  ldstr    aAllowreplaceme// "allowReplacementTokens"
0xa55f  ldstr    asc_3DBBA// ""
0xa564  ldc.i4.1
0xa565  box      [mscorlib]System.Boolean
0xa56a  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xa56f  ldarg.1
0xa570  ldstr    aSchemaSemantic// "Schema.SemanticModeling.xsd"
0xa575  ldstr    aSchemaSemantic_1// "Schema.SemanticModelingFragment.xslt"
0xa57a  ldloc.0
0xa57b  call     class [System.Xml]System.Xml.Schema.XmlSchema Microsoft.ReportingServices.Modeling.ModelingXmlSchema::ReadXmlSchemaWithTransform(string schemaName, string transformName, class [System.Xml]System.Xml.Xsl.XsltArgumentList arguments)
0xa580  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0xa585  pop
0xa586  ret
0xa587  ldstr    aUnknownSemanti// "Unknown SemanticModelingSchema instance"
0xa58c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xa591  throw
```
