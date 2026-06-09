# Microsoft.ReportingServices.Library.Soap2005.ModelDrillthroughReport::FromXml

- ea: `0x6fc20`
- end: `0x6fd40`
- name: `Microsoft.ReportingServices.Library.Soap2005.ModelDrillthroughReport::FromXml`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x31320`

## callees

- `0x6fb50`
- `0x6fc20`

## string_xrefs

- `0x6fc42`: `invalid XML element`
- `0x6fc67`: `invalid XML element name: {0}`
- `0x6fc9f`: `invalid XML element name: {0}`
- `0x6fcc3`: `invalid XML expected 2 attributes, found `
- `0x6fd2e`: `malformed XML`

## pseudocode

```c

```

## disassembly

```asm
0x6fc20  ldarg.0
0x6fc21  brtrue.s loc_6FC25
0x6fc23  ldnull
0x6fc24  ret
0x6fc25  ldarg.0
0x6fc26  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(string)
0x6fc2b  stloc.0
0x6fc2c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.Soap2005.ModelDrillthroughReport>::.ctor()
0x6fc31  stloc.1
0x6fc32  ldloc.0
0x6fc33  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x6fc38  pop
0x6fc39  ldloc.0
0x6fc3a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x6fc3f  ldc.i4.1
0x6fc40  beq.s    loc_6FC4D
0x6fc42  ldstr    aInvalidXmlElem// "invalid XML element"
0x6fc47  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x6fc4c  throw
0x6fc4d  ldloc.0
0x6fc4e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x6fc53  ldstr    aModeldrillthro// "ModelDrillthroughReports"
0x6fc58  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6fc5d  brfalse  loc_6FD21
0x6fc62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6fc67  ldstr    aInvalidXmlElem_0// "invalid XML element name: {0}"
0x6fc6c  ldloc.0
0x6fc6d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x6fc72  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6fc77  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x6fc7c  throw
0x6fc7d  ldloc.0
0x6fc7e  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x6fc83  brfalse  loc_6FD21
0x6fc88  ldloc.0
0x6fc89  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x6fc8e  ldstr    aModeldrillthro_0// "ModelDrillthroughReport"
0x6fc93  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6fc98  brfalse.s loc_6FCB5
0x6fc9a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6fc9f  ldstr    aInvalidXmlElem_0// "invalid XML element name: {0}"
0x6fca4  ldloc.0
0x6fca5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x6fcaa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6fcaf  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x6fcb4  throw
0x6fcb5  ldloc.0
0x6fcb6  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0x6fcbb  ldc.i4.2
0x6fcbc  beq.s    loc_6FCE8
0x6fcbe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6fcc3  ldstr    aInvalidXmlExpe// "invalid XML expected 2 attributes, foun"...
0x6fcc8  ldloc.0
0x6fcc9  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0x6fcce  box      [mscorlib]System.Int32
0x6fcd3  call     string [mscorlib]System.String::Concat(object, object)
0x6fcd8  call     T0x2B000001
0x6fcdd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6fce2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x6fce7  throw
0x6fce8  ldloc.0
0x6fce9  ldstr    aPath_0// "Path"
0x6fcee  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x6fcf3  stloc.2
0x6fcf4  ldtoken  Microsoft.ReportingServices.Library.Soap2005.DrillthroughType
0x6fcf9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fcfe  ldloc.0
0x6fcff  ldstr    aType_0// "Type"
0x6fd04  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x6fd09  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x6fd0e  unbox.any Microsoft.ReportingServices.Library.Soap2005.DrillthroughType
0x6fd13  stloc.3
0x6fd14  ldloc.1
0x6fd15  ldloc.2
0x6fd16  ldloc.3
0x6fd17  newobj   instance void Microsoft.ReportingServices.Library.Soap2005.ModelDrillthroughReport::.ctor(string path, valuetype Microsoft.ReportingServices.Library.Soap2005.DrillthroughType type)
0x6fd1c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.Soap2005.ModelDrillthroughReport>::Add(var<u1>)
0x6fd21  ldloc.0
0x6fd22  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x6fd27  brtrue   loc_6FC7D
0x6fd2c  leave.s  loc_6FD39
0x6fd2e  ldstr    aMalformedXml// "malformed XML"
0x6fd33  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x6fd38  throw
0x6fd39  ldloc.1
0x6fd3a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.Soap2005.ModelDrillthroughReport>::ToArray()
0x6fd3f  ret
```
