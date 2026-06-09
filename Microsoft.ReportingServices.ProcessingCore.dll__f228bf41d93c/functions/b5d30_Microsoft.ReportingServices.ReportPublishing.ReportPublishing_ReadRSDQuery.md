# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRSDQuery

- ea: `0xb5d30`
- end: `0xb5f05`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRSDQuery`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0xb59b0`

## callees

- `0x9d040`
- `0xa9f20`
- `0xa9f50`
- `0xaadb0`
- `0xadae0`
- `0xb5d30`
- `0xb9ed0`
- `0xb9ef0`
- `0xbb9a0`
- `0xbcdc0`
- `0xbcdd0`
- `0xbcde0`
- `0x113150`
- `0x113210`
- `0x1132d0`
- `0x113310`
- `0x116480`
- `0x1164a0`
- `0x1164d0`
- `0x1164e0`
- `0x116500`
- `0x116510`
- `0x116520`
- `0x116830`
- `0x16fc30`
- `0x170dc0`
- `0x187b10`
- `0x23f530`

## string_xrefs

- `0xb5d92`: `CommandType`
- `0xb5da0`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0xb5d30  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::.ctor()
0xb5d35  stloc.0
0xb5d36  ldarg.0
0xb5d37  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateID()
0xb5d3c  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::.ctor(int32 id)
0xb5d41  stloc.1
0xb5d42  ldc.i4.0
0xb5d43  stloc.2
0xb5d44  ldc.i4.0
0xb5d45  stloc.3
0xb5d46  ldnull
0xb5d47  stloc.s  4
0xb5d49  ldarg.0
0xb5d4a  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5d4f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xb5d54  pop
0xb5d55  ldarg.0
0xb5d56  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5d5b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xb5d60  stloc.s  5
0xb5d62  ldloc.s  5
0xb5d64  ldc.i4.1
0xb5d65  beq.s    loc_B5D75
0xb5d67  ldloc.s  5
0xb5d69  ldc.i4.s 0xF
0xb5d6b  beq      loc_B5E8A
0xb5d70  br       loc_B5EA3
0xb5d75  ldarg.0
0xb5d76  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5d7b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb5d80  stloc.s  7
0xb5d82  ldloc.s  7
0xb5d84  ldstr    aDatasourcerefe// "DataSourceReference"
0xb5d89  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5d8e  brtrue.s loc_B5DD3
0xb5d90  ldloc.s  7
0xb5d92  ldstr    aCommandtype// "CommandType"
0xb5d97  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5d9c  brtrue.s loc_B5DFF
0xb5d9e  ldloc.s  7
0xb5da0  ldstr    aCommandtext// "CommandText"
0xb5da5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5daa  brtrue.s loc_B5E10
0xb5dac  ldloc.s  7
0xb5dae  ldstr    aDatasetparamet_0// "DataSetParameters"
0xb5db3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5db8  brtrue   loc_B5E40
0xb5dbd  ldloc.s  7
0xb5dbf  ldstr    aTimeout// "Timeout"
0xb5dc4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5dc9  brtrue   loc_B5E5E
0xb5dce  br       loc_B5EA3
0xb5dd3  ldloc.1
0xb5dd4  ldarg.0
0xb5dd5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5dda  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xb5ddf  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::set_DataSourceReference(string value)
0xb5de4  ldloc.0
0xb5de5  ldloc.1
0xb5de6  ldstr    aDatasetdatasou// "DataSetDataSource"
0xb5deb  dup
0xb5dec  stloc.s  8
0xb5dee  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::set_Name(string value)
0xb5df3  ldloc.s  8
0xb5df5  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_DataSourceName(string value)
0xb5dfa  br       loc_B5EA3
0xb5dff  ldloc.0
0xb5e00  ldarg.0
0xb5e01  call     instance valuetype [System.Data]System.Data.CommandType Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadCommandType()
0xb5e06  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0xb5e0b  br       loc_B5EA3
0xb5e10  ldarga.s 1
0xb5e12  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb5e17  stloc.s  6
0xb5e19  ldarga.s 1
0xb5e1b  ldc.i4.s 0x16
0xb5e1d  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xb5e22  ldloc.0
0xb5e23  ldarg.0
0xb5e24  ldarg.1
0xb5e25  ldc.i4.s 0x12
0xb5e27  ldloca.s 3
0xb5e29  ldloc.s  4
0xb5e2b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQueryOrParameterExpression(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, valuetype Microsoft.ReportingServices.ReportProcessing.DataType dataType, bool& isComplex, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> parametersInQuery)
0xb5e30  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_CommandText(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xb5e35  ldarga.s 1
0xb5e37  ldloc.s  6
0xb5e39  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xb5e3e  br.s     loc_B5EA3
0xb5e40  ldloc.0
0xb5e41  ldarg.0
0xb5e42  ldarg.1
0xb5e43  ldloca.s 3
0xb5e45  ldloc.s  4
0xb5e47  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQueryParameters(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, bool& hasComplexParams, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> parametersInQuery)
0xb5e4c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_Parameters(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> value)
0xb5e51  ldloc.0
0xb5e52  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::get_Parameters()
0xb5e57  call     void Microsoft.ReportingServices.ReportProcessing.SharedDataSetParameterNameMapper::MakeUnique(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> queryParameters)
0xb5e5c  br.s     loc_B5EA3
0xb5e5e  ldloc.0
0xb5e5f  ldarg.0
0xb5e60  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5e65  ldarga.s 1
0xb5e67  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb5e6c  ldarga.s 1
0xb5e6e  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb5e73  ldarg.0
0xb5e74  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5e79  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb5e7e  callvirt instance int32 Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::ReadInteger(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName)
0xb5e83  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_TimeOut(int32 value)
0xb5e88  br.s     loc_B5EA3
0xb5e8a  ldstr    aQuery// "Query"
0xb5e8f  ldarg.0
0xb5e90  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5e95  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb5e9a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5e9f  brfalse.s loc_B5EA3
0xb5ea1  ldc.i4.1
0xb5ea2  stloc.2
0xb5ea3  ldloc.2
0xb5ea4  brfalse  loc_B5D49
0xb5ea9  ldloc.0
0xb5eaa  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::get_DataSourceName()
0xb5eaf  brfalse.s loc_B5F03
0xb5eb1  ldarg.0
0xb5eb2  ldarg.1
0xb5eb3  ldloc.1
0xb5eb4  call     instance class Microsoft.ReportingServices.DataExtensions.DataSourceInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::CreateSharedDataSourceLink(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource dataSource)
0xb5eb9  stloc.s  9
0xb5ebb  ldloc.s  9
0xb5ebd  brfalse.s loc_B5F03
0xb5ebf  ldarg.0
0xb5ec0  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0xb5ec5  callvirt instance class ResolveTemporaryDataSource Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_ResolveTemporaryDataSourceCallback()
0xb5eca  brfalse.s loc_B5EE9
0xb5ecc  ldarg.0
0xb5ecd  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0xb5ed2  callvirt instance class ResolveTemporaryDataSource Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_ResolveTemporaryDataSourceCallback()
0xb5ed7  ldloc.s  9
0xb5ed9  ldarg.0
0xb5eda  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0xb5edf  callvirt instance class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_OriginalDataSources()
0xb5ee4  callvirt instance void ResolveTemporaryDataSource::Invoke(class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo, class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection originalDataSources)
0xb5ee9  ldloc.1
0xb5eea  ldloc.s  9
0xb5eec  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ID()
0xb5ef1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::set_ID(valuetype [mscorlib]System.Guid value)
0xb5ef6  ldarg.0
0xb5ef7  ldfld    class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_dataSources
0xb5efc  ldloc.s  9
0xb5efe  callvirt instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection::Add(class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSource)
0xb5f03  ldloc.0
0xb5f04  ret
```
