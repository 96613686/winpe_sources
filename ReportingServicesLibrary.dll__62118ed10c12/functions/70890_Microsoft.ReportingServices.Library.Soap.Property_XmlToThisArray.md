# Microsoft.ReportingServices.Library.Soap.Property::XmlToThisArray

- ea: `0x70890`
- end: `0x709b0`
- name: `Microsoft.ReportingServices.Library.Soap.Property::XmlToThisArray`
- size: `288`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb8f0`
- `0xede0`
- `0x10470`
- `0x11750`
- `0x20b10`
- `0x26080`
- `0x2f090`
- `0x2f990`
- `0x2fc60`
- `0x32030`
- `0x37ca0`
- `0x37ff0`
- `0x381e0`
- `0x3b8f0`

## callees

- `0x70890`
- `0x709b0`

## string_xrefs

- `0x708b2`: `invalid XML element`
- `0x708d4`: `invalid XML element name: {0}`
- `0x7094d`: `malformed XML`
- `0x70938`: `invalid XML element `

## pseudocode

```c

```

## disassembly

```asm
0x70890  ldarg.0
0x70891  brtrue.s loc_70895
0x70893  ldnull
0x70894  ret
0x70895  newobj   instance void [mscorlib]System.Collections.SortedList::.ctor()
0x7089a  stloc.0
0x7089b  ldarg.0
0x7089c  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(string)
0x708a1  stloc.1
0x708a2  ldloc.1
0x708a3  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x708a8  pop
0x708a9  ldloc.1
0x708aa  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x708af  ldc.i4.1
0x708b0  beq.s    loc_708BD
0x708b2  ldstr    aInvalidXmlElem// "invalid XML element"
0x708b7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x708bc  throw
0x708bd  ldloc.1
0x708be  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x708c3  ldstr    aProperties_0// "Properties"
0x708c8  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x708cd  brfalse.s loc_70943
0x708cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x708d4  ldstr    aInvalidXmlElem_0// "invalid XML element name: {0}"
0x708d9  ldloc.1
0x708da  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x708df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x708e4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x708e9  throw
0x708ea  ldloc.1
0x708eb  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x708f0  brfalse.s loc_70943
0x708f2  ldloc.1
0x708f3  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x708f8  ldloc.1
0x708f9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x708fe  stloc.3
0x708ff  ldloc.3
0x70900  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::DecodePropertyName(string)
0x70905  stloc.3
0x70906  ldloc.1
0x70907  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x7090c  stloc.s  4
0x7090e  ldloc.s  4
0x70910  brfalse.s loc_7091B
0x70912  ldloc.s  4
0x70914  callvirt instance int32 [mscorlib]System.String::get_Length()
0x70919  brtrue.s loc_70925
0x7091b  ldloc.0
0x7091c  ldloc.3
0x7091d  ldnull
0x7091e  callvirt instance void [mscorlib]System.Collections.SortedList::Add(object, object)
0x70923  br.s     loc_7092E
0x70925  ldloc.0
0x70926  ldloc.3
0x70927  ldloc.s  4
0x70929  callvirt instance void [mscorlib]System.Collections.SortedList::Add(object, object)
0x7092e  brtrue.s loc_70943
0x70930  ldloc.1
0x70931  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x70936  brfalse.s loc_70943
0x70938  ldstr    aInvalidXmlElem_1// "invalid XML element "
0x7093d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x70942  throw
0x70943  ldloc.1
0x70944  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x70949  brtrue.s loc_708EA
0x7094b  leave.s  loc_70958
0x7094d  ldstr    aMalformedXml// "malformed XML"
0x70952  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x70957  throw
0x70958  ldloc.0
0x70959  callvirt instance int32 [mscorlib]System.Collections.SortedList::get_Count()
0x7095e  newarr   Microsoft.ReportingServices.Library.Soap.Property
0x70963  stloc.2
0x70964  ldc.i4.0
0x70965  stloc.s  5
0x70967  br.s     loc_709A4
0x70969  newobj   instance void Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x7096e  stloc.s  6
0x70970  ldloc.s  6
0x70972  ldloc.0
0x70973  ldloc.s  5
0x70975  callvirt instance object [mscorlib]System.Collections.SortedList::GetKey(int32)
0x7097a  castclass [mscorlib]System.String
0x7097f  stfld    string Microsoft.ReportingServices.Library.Soap.Property::Name
0x70984  ldloc.s  6
0x70986  ldloc.0
0x70987  ldloc.s  5
0x70989  callvirt instance object [mscorlib]System.Collections.SortedList::GetByIndex(int32)
0x7098e  castclass [mscorlib]System.String
0x70993  stfld    string Microsoft.ReportingServices.Library.Soap.Property::Value
0x70998  ldloc.2
0x70999  ldloc.s  5
0x7099b  ldloc.s  6
0x7099d  stelem.ref
0x7099e  ldloc.s  5
0x709a0  ldc.i4.1
0x709a1  add
0x709a2  stloc.s  5
0x709a4  ldloc.s  5
0x709a6  ldloc.0
0x709a7  callvirt instance int32 [mscorlib]System.Collections.SortedList::get_Count()
0x709ac  blt.s    loc_70969
0x709ae  ldloc.2
0x709af  ret
```
