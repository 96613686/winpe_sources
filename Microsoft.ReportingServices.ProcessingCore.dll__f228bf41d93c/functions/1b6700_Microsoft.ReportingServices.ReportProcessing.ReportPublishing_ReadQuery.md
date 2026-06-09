# Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadQuery

- ea: `0x1b6700`
- end: `0x1b6849`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadQuery`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b63f0`

## callees

- `0x198430`
- `0x198450`
- `0x198470`
- `0x198490`
- `0x1984f0`
- `0x198670`
- `0x1b4e50`
- `0x1b6700`
- `0x1b6850`
- `0x1b6920`
- `0x1c3380`
- `0x2643c0`
- `0x2643d0`
- `0x264b20`

## string_xrefs

- `0x1b6755`: `CommandType`
- `0x1b6763`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x1b6700  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportQuery::.ctor()
0x1b6705  stloc.0
0x1b6706  ldc.i4.0
0x1b6707  stloc.1
0x1b6708  ldc.i4.0
0x1b6709  stloc.2
0x1b670a  ldnull
0x1b670b  stloc.3
0x1b670c  ldarg.0
0x1b670d  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b6712  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1b6717  pop
0x1b6718  ldarg.0
0x1b6719  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b671e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1b6723  stloc.s  4
0x1b6725  ldloc.s  4
0x1b6727  ldc.i4.1
0x1b6728  beq.s    loc_1B6738
0x1b672a  ldloc.s  4
0x1b672c  ldc.i4.s 0xF
0x1b672e  beq      loc_1B6814
0x1b6733  br       loc_1B682D
0x1b6738  ldarg.0
0x1b6739  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b673e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1b6743  stloc.s  5
0x1b6745  ldloc.s  5
0x1b6747  ldstr    aDatasourcename// "DataSourceName"
0x1b674c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b6751  brtrue.s loc_1B6790
0x1b6753  ldloc.s  5
0x1b6755  ldstr    aCommandtype// "CommandType"
0x1b675a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b675f  brtrue.s loc_1B67A6
0x1b6761  ldloc.s  5
0x1b6763  ldstr    aCommandtext// "CommandText"
0x1b6768  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b676d  brtrue.s loc_1B67B4
0x1b676f  ldloc.s  5
0x1b6771  ldstr    aQueryparameter// "QueryParameters"
0x1b6776  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b677b  brtrue.s loc_1B67EE
0x1b677d  ldloc.s  5
0x1b677f  ldstr    aTimeout// "Timeout"
0x1b6784  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b6789  brtrue.s loc_1B6801
0x1b678b  br       loc_1B682D
0x1b6790  ldloc.0
0x1b6791  ldarg.0
0x1b6792  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b6797  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x1b679c  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportQuery::set_DataSourceName(string value)
0x1b67a1  br       loc_1B682D
0x1b67a6  ldloc.0
0x1b67a7  ldarg.0
0x1b67a8  call     instance valuetype [System.Data]System.Data.CommandType Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadCommandType()
0x1b67ad  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportQuery::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x1b67b2  br.s     loc_1B682D
0x1b67b4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1b67b9  ldc.i4.s 0x14
0x1b67bb  ldarga.s 1
0x1b67bd  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1b67c2  ceq
0x1b67c4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x1b67c9  ldarga.s 1
0x1b67cb  ldc.i4.s 0x16
0x1b67cd  call     instance void PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x1b67d2  ldloc.0
0x1b67d3  ldarg.0
0x1b67d4  ldarg.1
0x1b67d5  ldloca.s 2
0x1b67d7  ldloca.s 3
0x1b67d9  call     instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadQueryOrParameterExpression(valuetype PublishingContextStruct context, bool& isComplex, class Microsoft.ReportingServices.ReportProcessing.StringList& parametersInQuery)
0x1b67de  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportQuery::set_CommandText(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo value)
0x1b67e3  ldarga.s 1
0x1b67e5  ldc.i4.s 0x14
0x1b67e7  call     instance void PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x1b67ec  br.s     loc_1B682D
0x1b67ee  ldloc.0
0x1b67ef  ldarg.0
0x1b67f0  ldarg.1
0x1b67f1  ldloca.s 2
0x1b67f3  ldloca.s 3
0x1b67f5  call     instance class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadQueryParameters(valuetype PublishingContextStruct context, bool& hasComplexParams, class Microsoft.ReportingServices.ReportProcessing.StringList& parametersInQuery)
0x1b67fa  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportQuery::set_Parameters(class Microsoft.ReportingServices.ReportProcessing.ParameterValueList value)
0x1b67ff  br.s     loc_1B682D
0x1b6801  ldloc.0
0x1b6802  ldarg.0
0x1b6803  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b6808  callvirt instance int32 RmlValidatingReader::ReadInteger()
0x1b680d  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportQuery::set_TimeOut(int32 value)
0x1b6812  br.s     loc_1B682D
0x1b6814  ldstr    aQuery// "Query"
0x1b6819  ldarg.0
0x1b681a  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b681f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1b6824  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b6829  brfalse.s loc_1B682D
0x1b682b  ldc.i4.1
0x1b682c  stloc.1
0x1b682d  ldloc.1
0x1b682e  brfalse  loc_1B670C
0x1b6833  ldarg.2
0x1b6834  ldarg.0
0x1b6835  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSetList Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_dataSets
0x1b683a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1b683f  ldloc.2
0x1b6840  ldloc.3
0x1b6841  newobj   instance void Microsoft.ReportingServices.ReportProcessing.YukonDataSetInfo::.ctor(int32 index, bool isComplex, class Microsoft.ReportingServices.ReportProcessing.StringList parameterNames)
0x1b6846  stind.ref
0x1b6847  ldloc.0
0x1b6848  ret
```
