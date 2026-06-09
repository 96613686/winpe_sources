# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::Phase1

- ea: `0x9d120`
- end: `0x9d48b`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::Phase1`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x9cc30`

## callees

- `0x9d120`
- `0x9d490`
- `0x9d4c0`
- `0x9d500`
- `0xb9e20`
- `0xb9f20`
- `0xb9f40`
- `0xba850`
- `0xbcb20`
- `0xc1200`
- `0xc1470`
- `0xc15b0`
- `0x122060`
- `0x152a20`
- `0x153390`
- `0x167550`
- `0x16de50`
- `0x170a60`
- `0x175d50`
- `0x176790`
- `0x1767c0`

## string_xrefs

- `0x9d16c`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition`
- `0x9d184`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportdefinition`
- `0x9d19c`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0x9d1b4`: `http://schemas.microsoft.com/sqlserver/reporting/2013/01/reportdefinition`
- `0x9d154`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`
- `0x9d343`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`
- `0x9d159`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.ReportDefinition.xsd`
- `0x9d171`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.ReportDefinition2010.xsd`
- `0x9d189`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.ReportDefinition2011.xsd`
- `0x9d1a1`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.ReportDefinition2012.xsd`
- `0x9d1b9`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.ReportDefinition2013.xsd`
- `0x9d1cc`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition/defaultfontfamily`
- `0x9d1d1`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.DefaultFontFamily.xsd`
- `0x9d1e4`: `http://schemas.microsoft.com/sqlserver/reporting/webauthoring`
- `0x9d1e9`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.WebAuthoring.xsd`
- `0x9d1fc`: `http://schemas.microsoft.com/sqlserver/reporting/accessibilityproperties`
- `0x9d201`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.AccessibilityProperties.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x9d120  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x9d125  ldarg.0
0x9d126  ldfld    class Microsoft.ReportingServices.ReportPublishing.ReportUpgradeStrategy Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportUpgradeStrategy
0x9d12b  ldnull
0x9d12c  cgt.un
0x9d12e  ldstr    aThereIsNoUpgra// "There is no Upgrade Strategy for this s"...
0x9d133  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9d138  ldarg.0
0x9d139  ldfld    class Microsoft.ReportingServices.ReportPublishing.ReportUpgradeStrategy Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportUpgradeStrategy
0x9d13e  ldarg.1
0x9d13f  callvirt instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.ReportPublishing.ReportUpgradeStrategy::Upgrade(class [mscorlib]System.IO.Stream definitionStream)
0x9d144  stloc.0
0x9d145  ldloca.s 1
0x9d147  initobj  valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>
0x9d14d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::.ctor()
0x9d152  stloc.2
0x9d153  ldarg.0
0x9d154  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0x9d159  ldstr    aMicrosoftRepor_3// "Microsoft.ReportingServices.ReportProce"...
0x9d15e  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d163  stloc.1
0x9d164  ldloc.2
0x9d165  ldloc.1
0x9d166  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d16b  ldarg.0
0x9d16c  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0x9d171  ldstr    aMicrosoftRepor_4// "Microsoft.ReportingServices.ReportProce"...
0x9d176  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d17b  stloc.1
0x9d17c  ldloc.2
0x9d17d  ldloc.1
0x9d17e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d183  ldarg.0
0x9d184  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/sqlserver/"...
0x9d189  ldstr    aMicrosoftRepor_5// "Microsoft.ReportingServices.ReportProce"...
0x9d18e  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d193  stloc.1
0x9d194  ldloc.2
0x9d195  ldloc.1
0x9d196  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d19b  ldarg.0
0x9d19c  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0x9d1a1  ldstr    aMicrosoftRepor_6// "Microsoft.ReportingServices.ReportProce"...
0x9d1a6  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d1ab  stloc.1
0x9d1ac  ldloc.2
0x9d1ad  ldloc.1
0x9d1ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d1b3  ldarg.0
0x9d1b4  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0x9d1b9  ldstr    aMicrosoftRepor_7// "Microsoft.ReportingServices.ReportProce"...
0x9d1be  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d1c3  stloc.1
0x9d1c4  ldloc.2
0x9d1c5  ldloc.1
0x9d1c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d1cb  ldarg.0
0x9d1cc  ldstr    aHttpSchemasMic_8// "http://schemas.microsoft.com/sqlserver/"...
0x9d1d1  ldstr    aMicrosoftRepor_8// "Microsoft.ReportingServices.ReportProce"...
0x9d1d6  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d1db  stloc.1
0x9d1dc  ldloc.2
0x9d1dd  ldloc.1
0x9d1de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d1e3  ldarg.0
0x9d1e4  ldstr    aHttpSchemasMic_9// "http://schemas.microsoft.com/sqlserver/"...
0x9d1e9  ldstr    aMicrosoftRepor_9// "Microsoft.ReportingServices.ReportProce"...
0x9d1ee  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d1f3  stloc.1
0x9d1f4  ldloc.2
0x9d1f5  ldloc.1
0x9d1f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d1fb  ldarg.0
0x9d1fc  ldstr    aHttpSchemasMic_10// "http://schemas.microsoft.com/sqlserver/"...
0x9d201  ldstr    aMicrosoftRepor_10// "Microsoft.ReportingServices.ReportProce"...
0x9d206  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRDLNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0x9d20b  stloc.1
0x9d20c  ldloc.2
0x9d20d  ldloc.1
0x9d20e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0x9d213  ldarg.0
0x9d214  ldloc.0
0x9d215  ldloc.2
0x9d216  ldarg.0
0x9d217  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x9d21c  ldarg.0
0x9d21d  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0x9d222  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_IsRdlx()
0x9d227  brtrue.s loc_9D22C
0x9d229  ldc.i4.0
0x9d22a  br.s     loc_9D22D
0x9d22c  ldc.i4.1
0x9d22d  ldarg.0
0x9d22e  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0x9d233  callvirt instance class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_PublishingVersioning()
0x9d238  newobj   instance void Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::.ctor(class [mscorlib]System.IO.Stream stream, class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>> namespaceSchemaStreamMap, class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext errorContext, valuetype ItemType itemType, [opt] class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning publishingVersioning)
0x9d23d  stfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9d242  ldarg.0
0x9d243  ldc.i4   0x84
0x9d248  ldc.i4.s 0x4A
0x9d24a  ldc.i4   0x85
0x9d24f  newobj   instance void Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator::.ctor(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNotCLS, valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNotUnique, valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNameLength)
0x9d254  stfld    class Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportItemNames
0x9d259  ldarg.0
0x9d25a  ldc.i4   0x84
0x9d25f  ldc.i4   0x24A
0x9d264  ldc.i4   0x85
0x9d269  newobj   instance void Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator::.ctor(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNotCLS, valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNotUnique, valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCodeNameLength)
0x9d26e  stfld    class Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportSectionNames
0x9d273  ldarg.0
0x9d274  newobj   instance void Microsoft.ReportingServices.ReportPublishing.VariableNameValidator::.ctor()
0x9d279  stfld    class Microsoft.ReportingServices.ReportPublishing.VariableNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_variableNames
0x9d27e  ldarg.0
0x9d27f  newobj   instance void Microsoft.ReportingServices.ReportPublishing.ScopeNameValidator::.ctor()
0x9d284  stfld    class Microsoft.ReportingServices.ReportPublishing.ScopeNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_scopeNames
0x9d289  ldarg.0
0x9d28a  newobj   instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection::.ctor()
0x9d28f  stfld    class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_dataSources
0x9d294  ldarg.s  5
0x9d296  ldnull
0x9d297  stind.ref
0x9d298  ldarg.0
0x9d299  newobj   instance void Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection::.ctor()
0x9d29e  stfld    class Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_sharedDataSetReferences
0x9d2a3  ldarg.0
0x9d2a4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReport>::.ctor()
0x9d2a9  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReport> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_subReports
0x9d2ae  ldarg.0
0x9d2af  newobj   instance void Microsoft.ReportingServices.RdlExpressions.ExpressionUsage::.ctor()
0x9d2b4  stfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionUsage Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_expressionUsage
0x9d2b9  br.s     loc_9D313
0x9d2bb  ldc.i4.1
0x9d2bc  ldarg.0
0x9d2bd  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9d2c2  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x9d2c7  bne.un.s loc_9D313
0x9d2c9  ldstr    aReport// "Report"
0x9d2ce  ldarg.0
0x9d2cf  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9d2d4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9d2d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9d2de  brfalse.s loc_9D313
0x9d2e0  ldarg.0
0x9d2e1  ldarg.0
0x9d2e2  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x9d2e7  ldarg.0
0x9d2e8  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionUsage Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_expressionUsage
0x9d2ed  newobj   instance void Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::.ctor(class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, class Microsoft.ReportingServices.RdlExpressions.ExpressionUsage expressionUsage)
0x9d2f2  ldarg.0
0x9d2f3  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x9d2f8  newobj   instance void Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::.ctor(class Microsoft.ReportingServices.RdlExpressions.ExpressionParser langParser, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x9d2fd  stfld    class Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportCT
0x9d302  ldarg.0
0x9d303  ldarg.0
0x9d304  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0x9d309  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_DataProtection()
0x9d30e  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadReport(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x9d313  ldarg.0
0x9d314  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9d319  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x9d31e  brtrue.s loc_9D2BB
0x9d320  ldarg.0
0x9d321  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Report Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_report
0x9d326  brtrue.s loc_9D360
0x9d328  ldarg.0
0x9d329  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x9d32e  ldc.i4   0xB6
0x9d333  ldc.i4.0
0x9d334  ldc.i4.0
0x9d335  ldnull
0x9d336  ldstr    aNamespace// "Namespace"
0x9d33b  ldc.i4.1
0x9d33c  newarr   [mscorlib]System.String
0x9d341  dup
0x9d342  ldc.i4.0
0x9d343  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0x9d348  stelem.ref
0x9d349  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x9d34e  pop
0x9d34f  ldarg.0
0x9d350  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x9d355  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0x9d35a  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0x9d35f  throw
0x9d360  leave    loc_9D48A
0x9d365  stloc.3
0x9d366  ldarg.0
0x9d367  ldloc.3
0x9d368  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::CreateInvalidReportDefinitionException(class [mscorlib]System.Exception e)
0x9d36d  leave    loc_9D48A
0x9d372  stloc.s  4
0x9d374  ldarg.0
0x9d375  ldloc.s  4
0x9d377  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::CreateInvalidReportDefinitionException(class [mscorlib]System.Exception e)
0x9d37c  leave    loc_9D48A
0x9d381  stloc.s  5
0x9d383  ldarg.0
0x9d384  ldloc.s  5
0x9d386  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::CreateInvalidReportDefinitionException(class [mscorlib]System.Exception e)
0x9d38b  leave    loc_9D48A
0x9d390  stloc.s  6
0x9d392  ldarg.0
0x9d393  ldloc.s  6
0x9d395  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::CreateInvalidReportDefinitionException(class [mscorlib]System.Exception e)
0x9d39a  leave    loc_9D48A
0x9d39f  stloc.s  7
0x9d3a1  ldarg.0
0x9d3a2  ldloc.s  7
0x9d3a4  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::CreateInvalidReportDefinitionException(class [mscorlib]System.Exception e)
0x9d3a9  leave    loc_9D48A
0x9d3ae  ldarg.0
0x9d3af  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9d3b4  brfalse.s loc_9D3C8
0x9d3b6  ldarg.0
0x9d3b7  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9d3bc  callvirt instance void [System.Xml]System.Xml.XmlReader::Close()
0x9d3c1  ldarg.0
0x9d3c2  ldnull
0x9d3c3  stfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9d3c8  ldarg.2
0x9d3c9  ldarg.0
0x9d3ca  ldfld    string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_description
0x9d3cf  stind.ref
0x9d3d0  ldarg.3
0x9d3d1  ldnull
0x9d3d2  stind.ref
0x9d3d3  ldarg.0
0x9d3d4  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportLanguage
0x9d3d9  brfalse.s loc_9D3E8
0x9d3db  ldarg.3
0x9d3dc  ldarg.0
0x9d3dd  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportLanguage
0x9d3e2  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x9d3e7  stind.ref
0x9d3e8  ldarg.s  4
0x9d3ea  ldarg.0
0x9d3eb  ldfld    class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_dataSources
0x9d3f0  stind.ref
0x9d3f1  ldarg.s  5
0x9d3f3  ldarg.0
0x9d3f4  ldfld    class Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_sharedDataSetReferences
0x9d3f9  stind.ref
0x9d3fa  ldarg.s  6
0x9d3fc  ldarg.0
0x9d3fd  ldfld    bool Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_hasExternalImages
0x9d402  stind.i1
0x9d403  ldarg.s  7
0x9d405  ldarg.0
0x9d406  ldfld    bool Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_hasHyperlinks
0x9d40b  stind.i1
0x9d40c  ldarg.s  0xC
0x9d40e  ldarg.0
0x9d40f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Report Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_report
0x9d414  dup
0x9d415  brtrue.s loc_9D424
0x9d417  pop
0x9d418  ldloca.s 8
0x9d41a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9d420  ldloc.s  8
0x9d422  br.s     loc_9D443
0x9d424  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.Report::get_Code()
0x9d429  dup
0x9d42a  brtrue.s loc_9D439
0x9d42c  pop
0x9d42d  ldloca.s 8
0x9d42f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9d435  ldloc.s  8
0x9d437  br.s     loc_9D443
0x9d439  call     instance int32 [mscorlib]System.String::get_Length()
0x9d43e  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9d443  stobj    valuetype [mscorlib]System.Nullable`1<int32>
0x9d448  ldarg.s  8
0x9d44a  ldarg.0
0x9d44b  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionUsage Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_expressionUsage
0x9d450  stind.ref
0x9d451  ldarg.s  9
0x9d453  ldarg.0
0x9d454  ldfld    string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_webAuthoringVersion
0x9d459  stind.ref
0x9d45a  ldarg.s  0xA
0x9d45c  ldarg.0
0x9d45d  ldfld    string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_defaultView
0x9d462  stind.ref
0x9d463  ldarg.s  0xB
0x9d465  ldarg.0
0x9d466  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReport> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_subReports
0x9d46b  dup
0x9d46c  brtrue.s loc_9D472
0x9d46e  pop
0x9d46f  ldc.i4.0
0x9d470  br.s     loc_9D47A
0x9d472  call     instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReport>::get_Count()
0x9d477  ldc.i4.0
0x9d478  cgt
0x9d47a  stind.i1
0x9d47b  ldarg.0
0x9d47c  ldnull
0x9d47d  stfld    string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_description
0x9d482  ldarg.0
0x9d483  ldnull
  ... truncated ...
```
