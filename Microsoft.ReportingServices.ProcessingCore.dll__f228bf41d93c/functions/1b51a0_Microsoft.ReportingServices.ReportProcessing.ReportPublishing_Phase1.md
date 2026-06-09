# Microsoft.ReportingServices.ReportProcessing.ReportPublishing::Phase1

- ea: `0x1b51a0`
- end: `0x1b5397`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing::Phase1`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b5060`

## callees

- `0x170a60`
- `0x175d50`
- `0x176790`
- `0x1767c0`
- `0x18cb40`
- `0x18f300`
- `0x18f7a0`
- `0x1b51a0`
- `0x1b53a0`
- `0x1cd8b0`
- `0x1cda90`
- `0x1cdba0`
- `0x264ac0`

## string_xrefs

- `0x1b51bb`: `http://schemas.microsoft.com/sqlserver/reporting/2005/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0x1b51a0  ldarg.2
0x1b51a1  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(unsigned int8[])
0x1b51a6  stloc.0
0x1b51a7  ldloc.0
0x1b51a8  call     class [System.Xml]System.Xml.XmlReader [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.ReportProcessing.RDLUpgrader::UpgradeTo2005(class [System.Xml]System.Xml.XmlReader)
0x1b51ad  isinst   [System.Xml]System.Xml.XmlTextReader
0x1b51b2  stloc.0
0x1b51b3  ldarg.0
0x1b51b4  ldloc.0
0x1b51b5  ldarg.0
0x1b51b6  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b51bb  ldstr    aHttpSchemasMic_16// "http://schemas.microsoft.com/sqlserver/"...
0x1b51c0  call     class RmlValidatingReader RmlValidatingReader::CreateReader(class [System.Xml]System.Xml.XmlTextReader upgradedRDLReader, class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext errorContext, string targetRDLNamespace)
0x1b51c5  stfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b51ca  ldarg.0
0x1b51cb  ldc.i4   0x84
0x1b51d0  ldc.i4.s 0x4A
0x1b51d2  newobj   instance void Microsoft.ReportingServices.ReportProcessing.CLSUniqueNameValidator::.ctor(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNotCLS, valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNotUnique)
0x1b51d7  stfld    class Microsoft.ReportingServices.ReportProcessing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportItemNames
0x1b51dc  ldarg.0
0x1b51dd  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ScopeNameValidator::.ctor()
0x1b51e2  stfld    class Microsoft.ReportingServices.ReportProcessing.ScopeNameValidator Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_scopeNames
0x1b51e7  ldarg.0
0x1b51e8  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ImageStreamNames::.ctor()
0x1b51ed  stfld    class Microsoft.ReportingServices.ReportProcessing.ImageStreamNames Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_imageStreamNames
0x1b51f2  ldarg.0
0x1b51f3  ldarg.1
0x1b51f4  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportContext
0x1b51f9  ldarg.0
0x1b51fa  ldarg.3
0x1b51fb  stfld    class CreateReportChunk Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_createChunkCallback
0x1b5200  ldarg.0
0x1b5201  ldarg.s  4
0x1b5203  stfld    class CheckSharedDataSource Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_checkDataSourceCallback
0x1b5208  ldarg.0
0x1b5209  newobj   instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection::.ctor()
0x1b520e  stfld    class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_dataSources
0x1b5213  ldarg.0
0x1b5214  newobj   instance void Microsoft.ReportingServices.ReportProcessing.SubReportList::.ctor()
0x1b5219  stfld    class Microsoft.ReportingServices.ReportProcessing.SubReportList Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_subReports
0x1b521e  br.s     loc_1B5273
0x1b5220  ldc.i4.1
0x1b5221  ldarg.0
0x1b5222  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b5227  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1b522c  bne.un.s loc_1B5273
0x1b522e  ldstr    aReport// "Report"
0x1b5233  ldarg.0
0x1b5234  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b5239  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1b523e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b5243  brfalse.s loc_1B5273
0x1b5245  ldarg.0
0x1b5246  ldarg.0
0x1b5247  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b524c  newobj   instance void Microsoft.ReportingServices.ReportProcessing.VBExpressionParser::.ctor(class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1b5251  ldarg.0
0x1b5252  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b5257  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::.ctor(class Microsoft.ReportingServices.ReportProcessing.ExpressionParser langParser, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1b525c  stfld    class Microsoft.ReportingServices.ReportProcessing.ReportCompileTime Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportCT
0x1b5261  ldarg.0
0x1b5262  ldarg.0
0x1b5263  ldarg.s  5
0x1b5265  ldarg.s  6
0x1b5267  ldarg.s  7
0x1b5269  call     instance class Microsoft.ReportingServices.ReportProcessing.Report Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadReport(class ResolveTemporaryDataSource resolveTemporaryDataSourceCallback, class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection originalDataSources, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x1b526e  stfld    class Microsoft.ReportingServices.ReportProcessing.Report Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_report
0x1b5273  ldarg.0
0x1b5274  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b5279  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1b527e  brtrue.s loc_1B5220
0x1b5280  ldarg.0
0x1b5281  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_report
0x1b5286  brtrue.s loc_1B52C1
0x1b5288  ldarg.0
0x1b5289  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b528e  ldc.i4   0xB6
0x1b5293  ldc.i4.0
0x1b5294  ldc.i4.0
0x1b5295  ldnull
0x1b5296  ldstr    aNamespace// "Namespace"
0x1b529b  ldc.i4.1
0x1b529c  newarr   [mscorlib]System.String
0x1b52a1  dup
0x1b52a2  ldc.i4.0
0x1b52a3  ldarg.0
0x1b52a4  ldfld    string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_targetRDLNamespace
0x1b52a9  stelem.ref
0x1b52aa  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1b52af  pop
0x1b52b0  ldarg.0
0x1b52b1  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b52b6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0x1b52bb  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0x1b52c0  throw
0x1b52c1  leave    loc_1B5396
0x1b52c6  stloc.1
0x1b52c7  ldarg.0
0x1b52c8  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b52cd  ldc.i4   0x8F
0x1b52d2  ldc.i4.0
0x1b52d3  ldc.i4.0
0x1b52d4  ldnull
0x1b52d5  ldnull
0x1b52d6  ldc.i4.1
0x1b52d7  newarr   [mscorlib]System.String
0x1b52dc  dup
0x1b52dd  ldc.i4.0
0x1b52de  ldloc.1
0x1b52df  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1b52e4  stelem.ref
0x1b52e5  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1b52ea  pop
0x1b52eb  ldarg.0
0x1b52ec  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b52f1  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0x1b52f6  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0x1b52fb  throw
0x1b52fc  ldarg.0
0x1b52fd  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b5302  brfalse.s loc_1B5316
0x1b5304  ldarg.0
0x1b5305  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b530a  callvirt instance void [System.Xml]System.Xml.XmlReader::Close()
0x1b530f  ldarg.0
0x1b5310  ldnull
0x1b5311  stfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b5316  ldarg.0
0x1b5317  ldnull
0x1b5318  stfld    class Microsoft.ReportingServices.ReportProcessing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportItemNames
0x1b531d  ldarg.0
0x1b531e  ldnull
0x1b531f  stfld    class Microsoft.ReportingServices.ReportProcessing.ScopeNameValidator Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_scopeNames
0x1b5324  ldarg.0
0x1b5325  ldnull
0x1b5326  stfld    class Microsoft.ReportingServices.ReportProcessing.ImageStreamNames Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_imageStreamNames
0x1b532b  ldarg.0
0x1b532c  ldnull
0x1b532d  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportContext
0x1b5332  ldarg.0
0x1b5333  ldnull
0x1b5334  stfld    class CreateReportChunk Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_createChunkCallback
0x1b5339  ldarg.0
0x1b533a  ldnull
0x1b533b  stfld    class CheckSharedDataSource Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_checkDataSourceCallback
0x1b5340  ldarg.s  8
0x1b5342  ldarg.0
0x1b5343  ldfld    string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_description
0x1b5348  stind.ref
0x1b5349  ldarg.s  9
0x1b534b  ldnull
0x1b534c  stind.ref
0x1b534d  ldarg.0
0x1b534e  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportLanguage
0x1b5353  brfalse.s loc_1B5363
0x1b5355  ldarg.s  9
0x1b5357  ldarg.0
0x1b5358  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportLanguage
0x1b535d  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x1b5362  stind.ref
0x1b5363  ldarg.s  0xA
0x1b5365  ldarg.0
0x1b5366  ldfld    class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_dataSources
0x1b536b  stind.ref
0x1b536c  ldarg.s  0xB
0x1b536e  ldarg.0
0x1b536f  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.UserLocationFlags Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_userReferenceLocation
0x1b5374  stind.i4
0x1b5375  ldarg.s  0xC
0x1b5377  ldarg.0
0x1b5378  ldfld    bool Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_hasExternalImages
0x1b537d  stind.i1
0x1b537e  ldarg.s  0xD
0x1b5380  ldarg.0
0x1b5381  ldfld    bool Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_hasHyperlinks
0x1b5386  stind.i1
0x1b5387  ldarg.0
0x1b5388  ldnull
0x1b5389  stfld    string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_description
0x1b538e  ldarg.0
0x1b538f  ldnull
0x1b5390  stfld    class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_dataSources
0x1b5395  endfinally
0x1b5396  ret
```
