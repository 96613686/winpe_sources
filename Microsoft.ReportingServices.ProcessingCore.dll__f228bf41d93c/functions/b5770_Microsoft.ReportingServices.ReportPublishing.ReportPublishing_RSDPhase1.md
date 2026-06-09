# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::RSDPhase1

- ea: `0xb5770`
- end: `0xb58a1`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::RSDPhase1`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0xb5650`

## callees

- `0xb5770`
- `0xb58b0`
- `0xb58e0`
- `0xba850`
- `0x152a20`
- `0x167530`
- `0x170a60`
- `0x175d50`
- `0x176790`
- `0x1767c0`

## string_xrefs

- `0xb5792`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/shareddatasetdefinition`
- `0xb5797`: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing.SharedDataSetDefinition.xsd`

## pseudocode

```c

```

## disassembly

```asm
0xb5770  ldarg.0
0xb5771  newobj   instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection::.ctor()
0xb5776  stfld    class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_dataSources
0xb577b  ldarg.1
0xb577c  ldc.i4.0
0xb577d  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[], bool)
0xb5782  stloc.0
0xb5783  ldloca.s 1
0xb5785  initobj  valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>
0xb578b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::.ctor()
0xb5790  stloc.2
0xb5791  ldarg.0
0xb5792  ldstr    aHttpSchemasMic_11// "http://schemas.microsoft.com/sqlserver/"...
0xb5797  ldstr    aMicrosoftRepor_11// "Microsoft.ReportingServices.ReportProce"...
0xb579c  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetRSDNamespaceSchemaStreamPair(string validationNamespace, string xsdResource)
0xb57a1  stloc.1
0xb57a2  ldloc.2
0xb57a3  ldloc.1
0xb57a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>>::Add(var<u1>)
0xb57a9  ldarg.0
0xb57aa  ldloc.0
0xb57ab  ldloc.2
0xb57ac  ldarg.0
0xb57ad  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb57b2  ldc.i4.2
0xb57b3  ldnull
0xb57b4  newobj   instance void Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::.ctor(class [mscorlib]System.IO.Stream stream, class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, class [mscorlib]System.IO.Stream>> namespaceSchemaStreamMap, class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext errorContext, valuetype ItemType itemType, [opt] class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning publishingVersioning)
0xb57b9  stfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb57be  br.s     loc_B5807
0xb57c0  ldc.i4.1
0xb57c1  ldarg.0
0xb57c2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb57c7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xb57cc  bne.un.s loc_B5807
0xb57ce  ldstr    aShareddataset// "SharedDataSet"
0xb57d3  ldarg.0
0xb57d4  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb57d9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb57de  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb57e3  brfalse.s loc_B5807
0xb57e5  ldarg.0
0xb57e6  ldarg.0
0xb57e7  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb57ec  newobj   instance void Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::.ctor(class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xb57f1  ldarg.0
0xb57f2  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb57f7  newobj   instance void Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::.ctor(class Microsoft.ReportingServices.RdlExpressions.ExpressionParser langParser, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xb57fc  stfld    class Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportCT
0xb5801  ldarg.0
0xb5802  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRSDSharedDataSet()
0xb5807  ldarg.0
0xb5808  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb580d  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xb5812  brtrue.s loc_B57C0
0xb5814  ldarg.0
0xb5815  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_dataSetCore
0xb581a  brtrue.s loc_B584C
0xb581c  ldarg.0
0xb581d  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb5822  ldc.i4   0x1FB
0xb5827  ldc.i4.0
0xb5828  ldc.i4.s 0x26
0xb582a  ldnull
0xb582b  ldstr    aNamespace// "Namespace"
0xb5830  call     T0x2B000001
0xb5835  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb583a  pop
0xb583b  ldarg.0
0xb583c  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb5841  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0xb5846  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0xb584b  throw
0xb584c  leave.s  loc_B58A0
0xb584e  stloc.3
0xb584f  ldarg.0
0xb5850  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb5855  ldc.i4   0x1FC
0xb585a  ldc.i4.0
0xb585b  ldc.i4.s 0x26
0xb585d  ldnull
0xb585e  ldnull
0xb585f  ldc.i4.1
0xb5860  newarr   [mscorlib]System.String
0xb5865  dup
0xb5866  ldc.i4.0
0xb5867  ldloc.3
0xb5868  callvirt instance string [mscorlib]System.Exception::get_Message()
0xb586d  stelem.ref
0xb586e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb5873  pop
0xb5874  ldarg.0
0xb5875  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb587a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0xb587f  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0xb5884  throw
0xb5885  ldarg.0
0xb5886  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb588b  brfalse.s loc_B589F
0xb588d  ldarg.0
0xb588e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5893  callvirt instance void [System.Xml]System.Xml.XmlReader::Close()
0xb5898  ldarg.0
0xb5899  ldnull
0xb589a  stfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb589f  endfinally
0xb58a0  ret
```
