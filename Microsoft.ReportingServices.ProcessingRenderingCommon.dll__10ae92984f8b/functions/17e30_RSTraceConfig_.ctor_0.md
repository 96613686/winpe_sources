# RSTraceConfig::.ctor_0

- ea: `0x17e30`
- end: `0x180b1`
- name: `RSTraceConfig::.ctor_0`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18200`

## callees

- `0x17de0`
- `0x17e30`
- `0x180d0`
- `0x180f0`
- `0x18110`
- `0x18130`
- `0x18170`
- `0x18190`
- `0x181b0`
- `0x181d0`

## string_xrefs

- `0x17e3f`: `configDoc`
- `0x17e4b`: `/configuration/system.diagnostics/switches`
- `0x17ee4`: `/configuration/RStrace`
- `0x17f53`: `Reading trace settings {0}={1}`
- `0x18015`: `COMPONENTS`
- `0x18025`: `DIRECTORY`

## pseudocode

```c

```

## disassembly

```asm
0x17e30  ldarg.0
0x17e31  call     instance void [mscorlib]System.Object::.ctor()
0x17e36  ldarg.0
0x17e37  call     instance void RSTraceConfig::SetDefaultValues()
0x17e3c  ldarg.1
0x17e3d  brtrue.s loc_17E4A
0x17e3f  ldstr    aConfigdoc// "configDoc"
0x17e44  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17e49  throw
0x17e4a  ldarg.1
0x17e4b  ldstr    aConfigurationS// "/configuration/system.diagnostics/switc"...
0x17e50  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17e55  stloc.0
0x17e56  ldloc.0
0x17e57  brfalse  loc_17EE3
0x17e5c  ldloc.0
0x17e5d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x17e62  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x17e67  stloc.2
0x17e68  br.s     loc_17EC5
0x17e6a  ldloc.2
0x17e6b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x17e70  castclass [System.Xml]System.Xml.XmlNode
0x17e75  dup
0x17e76  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17e7b  ldstr    aName// "name"
0x17e80  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17e85  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17e8a  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x17e8f  stloc.3
0x17e90  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17e95  ldstr    aValue// "value"
0x17e9a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17e9f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17ea4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17ea9  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x17eae  stloc.s  4
0x17eb0  ldloc.3
0x17eb1  ldstr    aDefaulttracesw// "DEFAULTTRACESWITCH"
0x17eb6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17ebb  brfalse.s loc_17EC5
0x17ebd  ldarg.0
0x17ebe  ldloc.s  4
0x17ec0  call     instance void RSTraceConfig::set_DefaultTraceSwitch(string value)
0x17ec5  ldloc.2
0x17ec6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17ecb  brtrue.s loc_17E6A
0x17ecd  leave.s  loc_17EE3
0x17ecf  ldloc.2
0x17ed0  isinst   [mscorlib]System.IDisposable
0x17ed5  stloc.s  5
0x17ed7  ldloc.s  5
0x17ed9  brfalse.s loc_17EE2
0x17edb  ldloc.s  5
0x17edd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17ee2  endfinally
0x17ee3  ldarg.1
0x17ee4  ldstr    aConfigurationR// "/configuration/RStrace"
0x17ee9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17eee  stloc.1
0x17eef  ldloc.1
0x17ef0  brfalse  loc_180B0
0x17ef5  ldloc.1
0x17ef6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x17efb  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x17f00  stloc.2
0x17f01  br       loc_1808F
0x17f06  ldloc.2
0x17f07  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x17f0c  castclass [System.Xml]System.Xml.XmlNode
0x17f11  dup
0x17f12  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17f17  ldstr    aName// "name"
0x17f1c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17f21  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17f26  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x17f2b  stloc.s  6
0x17f2d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17f32  ldstr    aValue// "value"
0x17f37  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17f3c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17f41  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17f46  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x17f4b  stloc.s  7
0x17f4d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x17f52  ldc.i4.4
0x17f53  ldstr    aReadingTraceSe// "Reading trace settings {0}={1}"
0x17f58  ldc.i4.2
0x17f59  newarr   [mscorlib]System.Object
0x17f5e  dup
0x17f5f  ldc.i4.0
0x17f60  ldloc.s  6
0x17f62  stelem.ref
0x17f63  dup
0x17f64  ldc.i4.1
0x17f65  ldloc.s  7
0x17f67  stelem.ref
0x17f68  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x17f6d  ldloc.s  6
0x17f6f  brfalse  loc_1808F
0x17f74  ldloc.s  6
0x17f76  call     instance int32 [mscorlib]System.String::get_Length()
0x17f7b  stloc.s  9
0x17f7d  ldloc.s  9
0x17f7f  ldc.i4.6
0x17f80  sub
0x17f81  switch   loc_17FDD, loc_1808F, loc_1808F, loc_18023, loc_18013, loc_1808F, loc_1808F, loc_18003, loc_17FF0, loc_17FB7, loc_17FCA
0x17fb2  br       loc_1808F
0x17fb7  ldloc.s  6
0x17fb9  ldstr    aFilesizelimitm// "FILESIZELIMITMB"
0x17fbe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17fc3  brtrue.s loc_18033
0x17fc5  br       loc_1808F
0x17fca  ldloc.s  6
0x17fcc  ldstr    aKeepfilesforda// "KEEPFILESFORDAYS"
0x17fd1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17fd6  brtrue.s loc_18055
0x17fd8  br       loc_1808F
0x17fdd  ldloc.s  6
0x17fdf  ldstr    aPrefix// "PREFIX"
0x17fe4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17fe9  brtrue.s loc_1805F
0x17feb  br       loc_1808F
0x17ff0  ldloc.s  6
0x17ff2  ldstr    aTracelisteners// "TRACELISTENERS"
0x17ff7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17ffc  brtrue.s loc_18069
0x17ffe  br       loc_1808F
0x18003  ldloc.s  6
0x18005  ldstr    aTracefilemode// "TRACEFILEMODE"
0x1800a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1800f  brtrue.s loc_18073
0x18011  br.s     loc_1808F
0x18013  ldloc.s  6
0x18015  ldstr    aComponents// "COMPONENTS"
0x1801a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1801f  brtrue.s loc_1807D
0x18021  br.s     loc_1808F
0x18023  ldloc.s  6
0x18025  ldstr    aDirectory// "DIRECTORY"
0x1802a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1802f  brtrue.s loc_18087
0x18031  br.s     loc_1808F
0x18033  ldloc.s  7
0x18035  ldc.i4.7
0x18036  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1803b  ldloca.s 8
0x1803d  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x18042  pop
0x18043  ldarg.0
0x18044  ldloc.s  8
0x18046  ldc.i4.0
0x18047  bgt.s    loc_1804C
0x18049  ldc.i4.1
0x1804a  br.s     loc_1804E
0x1804c  ldloc.s  8
0x1804e  call     instance void RSTraceConfig::set_FileSizeLimitMB(int32 value)
0x18053  br.s     loc_1808F
0x18055  ldarg.0
0x18056  ldloc.s  7
0x18058  call     instance void RSTraceConfig::set_KeepFilesForDays(string value)
0x1805d  br.s     loc_1808F
0x1805f  ldarg.0
0x18060  ldloc.s  7
0x18062  call     instance void RSTraceConfig::set_Prefix(string value)
0x18067  br.s     loc_1808F
0x18069  ldarg.0
0x1806a  ldloc.s  7
0x1806c  call     instance void RSTraceConfig::set_TraceListeners(string value)
0x18071  br.s     loc_1808F
0x18073  ldarg.0
0x18074  ldloc.s  7
0x18076  call     instance void RSTraceConfig::set_TraceFileMode(string value)
0x1807b  br.s     loc_1808F
0x1807d  ldarg.0
0x1807e  ldloc.s  7
0x18080  call     instance void RSTraceConfig::set_Components(string value)
0x18085  br.s     loc_1808F
0x18087  ldarg.0
0x18088  ldloc.s  7
0x1808a  call     instance void RSTraceConfig::set_Directory(string value)
0x1808f  ldloc.2
0x18090  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18095  brtrue   loc_17F06
0x1809a  leave.s  loc_180B0
0x1809c  ldloc.2
0x1809d  isinst   [mscorlib]System.IDisposable
0x180a2  stloc.s  5
0x180a4  ldloc.s  5
0x180a6  brfalse.s loc_180AF
0x180a8  ldloc.s  5
0x180aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x180af  endfinally
0x180b0  ret
```
