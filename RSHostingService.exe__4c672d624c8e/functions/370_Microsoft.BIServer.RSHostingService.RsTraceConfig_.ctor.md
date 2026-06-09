# Microsoft.BIServer.RSHostingService.RsTraceConfig::.ctor

- ea: `0x370`
- end: `0x6b6`
- name: `Microsoft.BIServer.RSHostingService.RsTraceConfig::.ctor`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x360`

## callees

- `0x370`
- `0x6d0`
- `0x6f0`
- `0x710`
- `0x730`
- `0x750`
- `0x770`
- `0x790`
- `0x7b0`
- `0x7d0`
- `0x2d10`

## string_xrefs

- `0x3ef`: `/configuration/system.diagnostics/switches`
- `0x48a`: `/configuration/RStrace`
- `0x602`: `COMPONENTS`
- `0x615`: `DIRECTORY`

## pseudocode

```c

```

## disassembly

```asm
0x370  ldarg.0
0x371  call     instance void [mscorlib]System.Object::.ctor()
0x376  ldarg.1
0x377  brtrue.s loc_384
0x379  ldstr    aContents// "contents"
0x37e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x383  throw
0x384  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x389  stloc.0
0x38a  ldloc.0
0x38b  ldarg.1
0x38c  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x391  ldarg.0
0x392  ldstr    aDebugwindowFil// "debugwindow, file"
0x397  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_TraceListeners(string value)
0x39c  ldarg.0
0x39d  ldstr    aTidTime// "tid, time"
0x3a2  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_Prefix(string value)
0x3a7  ldarg.0
0x3a8  ldsfld   string [mscorlib]System.String::Empty
0x3ad  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_Directory(string value)
0x3b2  ldarg.0
0x3b3  ldsfld   string [mscorlib]System.String::Empty
0x3b8  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_FileName(string value)
0x3bd  ldarg.0
0x3be  ldstr    aUnique// "unique"
0x3c3  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_TraceFileMode(string value)
0x3c8  ldarg.0
0x3c9  ldstr    aAll3// "all:3"
0x3ce  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_Components(string value)
0x3d3  ldarg.0
0x3d4  ldstr    a3// "3"
0x3d9  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_DefaultTraceSwitch(string value)
0x3de  ldarg.0
0x3df  ldc.i4.s 0x20
0x3e1  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_FileSizeLimitMb(int32 value)
0x3e6  ldarg.0
0x3e7  ldc.i4.s 0xE
0x3e9  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_KeepFilesForDays(int32 value)
0x3ee  ldloc.0
0x3ef  ldstr    aConfigurationS_1// "/configuration/system.diagnostics/switc"...
0x3f4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f9  stloc.1
0x3fa  ldloc.1
0x3fb  brfalse  loc_489
0x400  ldloc.1
0x401  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x406  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x40b  stloc.3
0x40c  br.s     loc_46B
0x40e  ldloc.3
0x40f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x414  castclass [System.Xml]System.Xml.XmlNode
0x419  dup
0x41a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x41f  ldstr    aName// "name"
0x424  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x429  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x42e  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x433  stloc.s  4
0x435  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x43a  ldstr    aValue// "value"
0x43f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x444  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x449  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44e  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x453  stloc.s  5
0x455  ldloc.s  4
0x457  ldstr    aDefaulttracesw// "DEFAULTTRACESWITCH"
0x45c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x461  brfalse.s loc_46B
0x463  ldarg.0
0x464  ldloc.s  5
0x466  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_DefaultTraceSwitch(string value)
0x46b  ldloc.3
0x46c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x471  brtrue.s loc_40E
0x473  leave.s  loc_489
0x475  ldloc.3
0x476  isinst   [mscorlib]System.IDisposable
0x47b  stloc.s  6
0x47d  ldloc.s  6
0x47f  brfalse.s loc_488
0x481  ldloc.s  6
0x483  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x488  endfinally
0x489  ldloc.0
0x48a  ldstr    aConfigurationR// "/configuration/RStrace"
0x48f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x494  stloc.2
0x495  ldloc.2
0x496  brfalse  loc_6B5
0x49b  ldloc.2
0x49c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x4a1  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x4a6  stloc.3
0x4a7  br       loc_694
0x4ac  ldloc.3
0x4ad  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4b2  castclass [System.Xml]System.Xml.XmlNode
0x4b7  dup
0x4b8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4bd  ldstr    aName// "name"
0x4c2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4c7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4cc  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4d1  stloc.s  7
0x4d3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4d8  ldstr    aValue// "value"
0x4dd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4e2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ec  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x4f1  stloc.s  8
0x4f3  ldloc.s  7
0x4f5  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x4fa  stloc.s  9
0x4fc  ldloc.s  9
0x4fe  ldc.i4   0xAB95F408
0x503  bgt.un.s loc_545
0x505  ldloc.s  9
0x507  ldc.i4   0x7820AA89
0x50c  bgt.un.s loc_52B
0x50e  ldloc.s  9
0x510  ldc.i4   0x6E5ABDE9
0x515  beq      loc_600
0x51a  ldloc.s  9
0x51c  ldc.i4   0x7820AA89
0x521  beq      loc_5C1
0x526  br       loc_694
0x52b  ldloc.s  9
0x52d  ldc.i4   0x8404199B
0x532  beq      loc_5ED
0x537  ldloc.s  9
0x539  ldc.i4   0xAB95F408
0x53e  beq.s    loc_57F
0x540  br       loc_694
0x545  ldloc.s  9
0x547  ldc.i4   0xDA4BEE53
0x54c  bgt.un.s loc_568
0x54e  ldloc.s  9
0x550  ldc.i4   0xB7740FA8
0x555  beq      loc_613
0x55a  ldloc.s  9
0x55c  ldc.i4   0xDA4BEE53
0x561  beq.s    loc_5D7
0x563  br       loc_694
0x568  ldloc.s  9
0x56a  ldc.i4   0xE3C22A39
0x56f  beq.s    loc_5AB
0x571  ldloc.s  9
0x573  ldc.i4   0xFFA33252
0x578  beq.s    loc_595
0x57a  br       loc_694
0x57f  ldloc.s  7
0x581  ldstr    aFilename// "FILENAME"
0x586  call     bool [mscorlib]System.String::op_Equality(string, string)
0x58b  brtrue   loc_623
0x590  br       loc_694
0x595  ldloc.s  7
0x597  ldstr    aFilesizelimitm// "FILESIZELIMITMB"
0x59c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5a1  brtrue   loc_62D
0x5a6  br       loc_694
0x5ab  ldloc.s  7
0x5ad  ldstr    aKeepfilesforda// "KEEPFILESFORDAYS"
0x5b2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5b7  brtrue   loc_64F
0x5bc  br       loc_694
0x5c1  ldloc.s  7
0x5c3  ldstr    aPrefix// "PREFIX"
0x5c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5cd  brtrue   loc_664
0x5d2  br       loc_694
0x5d7  ldloc.s  7
0x5d9  ldstr    aTracelisteners// "TRACELISTENERS"
0x5de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e3  brtrue   loc_66E
0x5e8  br       loc_694
0x5ed  ldloc.s  7
0x5ef  ldstr    aTracefilemode// "TRACEFILEMODE"
0x5f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5f9  brtrue.s loc_678
0x5fb  br       loc_694
0x600  ldloc.s  7
0x602  ldstr    aComponents// "COMPONENTS"
0x607  call     bool [mscorlib]System.String::op_Equality(string, string)
0x60c  brtrue.s loc_682
0x60e  br       loc_694
0x613  ldloc.s  7
0x615  ldstr    aDirectory// "DIRECTORY"
0x61a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x61f  brtrue.s loc_68C
0x621  br.s     loc_694
0x623  ldarg.0
0x624  ldloc.s  8
0x626  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_FileName(string value)
0x62b  br.s     loc_694
0x62d  ldloc.s  8
0x62f  ldc.i4.7
0x630  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x635  ldloca.s 0xA
0x637  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x63c  pop
0x63d  ldarg.0
0x63e  ldloc.s  0xA
0x640  ldc.i4.0
0x641  bgt.s    loc_646
0x643  ldc.i4.1
0x644  br.s     loc_648
0x646  ldloc.s  0xA
0x648  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_FileSizeLimitMb(int32 value)
0x64d  br.s     loc_694
0x64f  ldloc.s  8
0x651  ldloca.s 0xB
0x653  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x658  brfalse.s loc_694
0x65a  ldarg.0
0x65b  ldloc.s  0xB
0x65d  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_KeepFilesForDays(int32 value)
0x662  br.s     loc_694
0x664  ldarg.0
0x665  ldloc.s  8
0x667  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_Prefix(string value)
0x66c  br.s     loc_694
0x66e  ldarg.0
0x66f  ldloc.s  8
0x671  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_TraceListeners(string value)
0x676  br.s     loc_694
0x678  ldarg.0
0x679  ldloc.s  8
0x67b  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_TraceFileMode(string value)
0x680  br.s     loc_694
0x682  ldarg.0
0x683  ldloc.s  8
0x685  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_Components(string value)
0x68a  br.s     loc_694
0x68c  ldarg.0
0x68d  ldloc.s  8
0x68f  call     instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::set_Directory(string value)
0x694  ldloc.3
0x695  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69a  brtrue   loc_4AC
0x69f  leave.s  loc_6B5
0x6a1  ldloc.3
0x6a2  isinst   [mscorlib]System.IDisposable
0x6a7  stloc.s  6
0x6a9  ldloc.s  6
0x6ab  brfalse.s loc_6B4
0x6ad  ldloc.s  6
0x6af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b4  endfinally
0x6b5  ret
```
