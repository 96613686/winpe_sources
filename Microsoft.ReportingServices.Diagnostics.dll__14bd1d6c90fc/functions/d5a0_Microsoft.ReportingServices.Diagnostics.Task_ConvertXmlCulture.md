# Microsoft.ReportingServices.Diagnostics.Task::ConvertXmlCulture

- ea: `0xd5a0`
- end: `0xd6c8`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ConvertXmlCulture`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd530`
- `0xd5a0`

## pseudocode

```c

```

## disassembly

```asm
0xd5a0  ldarg.0
0xd5a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd5a6  brtrue.s loc_D5B0
0xd5a8  ldarg.0
0xd5a9  call     bool Microsoft.ReportingServices.Diagnostics.Task::IsSharedSchedule(string xml)
0xd5ae  brfalse.s loc_D5B2
0xd5b0  ldarg.0
0xd5b1  ret
0xd5b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5b7  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xd5bc  stloc.0
0xd5bd  ldnull
0xd5be  stloc.1
0xd5bf  ldnull
0xd5c0  stloc.2
0xd5c1  ldarg.0
0xd5c2  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(string)
0xd5c7  stloc.1
0xd5c8  ldloc.1
0xd5c9  ldc.i4.2
0xd5ca  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_WhitespaceHandling(valuetype [System.Xml]System.Xml.WhitespaceHandling)
0xd5cf  ldloc.0
0xd5d0  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xd5d5  stloc.2
0xd5d6  ldsfld   string [mscorlib]System.String::Empty
0xd5db  stloc.s  5
0xd5dd  ldc.i4.1
0xd5de  ldarg.1
0xd5df  bne.un.s loc_D5F3
0xd5e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5e6  stloc.3
0xd5e7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_ClientPrimaryCulture()
0xd5ec  stloc.s  4
0xd5ee  br       loc_D69B
0xd5f3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_ClientPrimaryCulture()
0xd5f8  stloc.3
0xd5f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5fe  stloc.s  4
0xd600  br       loc_D69B
0xd605  ldc.i4.s 0x11
0xd607  ldloc.1
0xd608  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd60d  bne.un.s loc_D61B
0xd60f  ldloc.2
0xd610  ldc.i4.1
0xd611  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartDocument(bool)
0xd616  br       loc_D69B
0xd61b  ldloc.1
0xd61c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd621  ldc.i4.1
0xd622  bne.un.s loc_D642
0xd624  ldloc.2
0xd625  ldloc.1
0xd626  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xd62b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xd630  ldloc.2
0xd631  ldloc.1
0xd632  ldc.i4.0
0xd633  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributes(class [System.Xml]System.Xml.XmlReader, bool)
0xd638  ldloc.1
0xd639  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xd63e  stloc.s  5
0xd640  br.s     loc_D69B
0xd642  ldloc.1
0xd643  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd648  ldc.i4.3
0xd649  bne.un.s loc_D68B
0xd64b  ldloc.1
0xd64c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xd651  stloc.s  6
0xd653  ldstr    aDays// "Days"
0xd658  ldloc.s  5
0xd65a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd65f  brfalse.s loc_D681
0xd661  ldloc.s  6
0xd663  ldloc.3
0xd664  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xd669  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xd66e  ldloc.s  4
0xd670  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xd675  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xd67a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd67f  stloc.s  6
0xd681  ldloc.2
0xd682  ldloc.s  6
0xd684  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xd689  br.s     loc_D69B
0xd68b  ldloc.1
0xd68c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd691  ldc.i4.s 0xF
0xd693  bne.un.s loc_D69B
0xd695  ldloc.2
0xd696  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xd69b  ldloc.1
0xd69c  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xd6a1  brtrue   loc_D605
0xd6a6  leave.s  loc_D6C1
0xd6a8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MalformedXmlException::.ctor(class [System.Xml]System.Xml.XmlException)
0xd6ad  throw
0xd6ae  ldloc.1
0xd6af  brfalse.s loc_D6B7
0xd6b1  ldloc.1
0xd6b2  callvirt instance void [System.Xml]System.Xml.XmlReader::Close()
0xd6b7  ldloc.2
0xd6b8  brfalse.s loc_D6C0
0xd6ba  ldloc.2
0xd6bb  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0xd6c0  endfinally
0xd6c1  ldloc.0
0xd6c2  callvirt instance string [mscorlib]System.Object::ToString()
0xd6c7  ret
```
