# Microsoft.ReportingServices.Diagnostics.Canonicalization::AddFilesInManifest

- ea: `0xf70`
- end: `0x10eb`
- name: `Microsoft.ReportingServices.Diagnostics.Canonicalization::AddFilesInManifest`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xeb0`

## callees

- `0xf70`
- `0x10f0`

## string_xrefs

- `0xf90`: `Report Builder manifest file {0} not found.`
- `0x10c9`: `AddFilesInManifest: unexpected exception when parsing {0}. Exception is {1}.`

## pseudocode

```c

```

## disassembly

```asm
0xf70  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xf75  stloc.0
0xf76  ldarg.0
0xf77  call     bool [mscorlib]System.IO.File::Exists(string)
0xf7c  brtrue.s loc_FA5
0xf7e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_HttpRuntimeTracer()
0xf83  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0xf88  brfalse.s loc_FA4
0xf8a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_HttpRuntimeTracer()
0xf8f  ldc.i4.3
0xf90  ldstr    aReportBuilderM// "Report Builder manifest file {0} not fo"...
0xf95  ldc.i4.1
0xf96  newarr   [mscorlib]System.Object
0xf9b  dup
0xf9c  ldc.i4.0
0xf9d  ldarg.0
0xf9e  stelem.ref
0xf9f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xfa4  ret
0xfa5  nop
0xfa6  ldloc.0
0xfa7  ldarg.0
0xfa8  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentFile(class [System.Xml]System.Xml.XmlDocument, string)
0xfad  ldloc.0
0xfae  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xfb3  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xfb8  stloc.1
0xfb9  ldloc.0
0xfba  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xfbf  stloc.2
0xfc0  ldloc.2
0xfc1  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0xfc6  ldsfld   string [mscorlib]System.String::Empty
0xfcb  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetNamespace(string)
0xfd0  stloc.3
0xfd1  ldloc.1
0xfd2  ldstr    aDefault// "default"
0xfd7  ldloc.3
0xfd8  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xfdd  ldloc.2
0xfde  ldsfld   string Microsoft.ReportingServices.Diagnostics.Canonicalization::XPathAssembly
0xfe3  ldloc.1
0xfe4  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xfe9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xfee  stloc.s  4
0xff0  br.s     loc_1028
0xff2  ldloc.s  4
0xff4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xff9  castclass [System.Xml]System.Xml.XmlNode
0xffe  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1003  ldstr    aCodebase// "codebase"
0x1008  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x100d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1012  stloc.s  5
0x1014  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.Diagnostics.Canonicalization::m_reportbuilderFiles
0x1019  ldloc.s  5
0x101b  ldarg.1
0x101c  ldc.i4.1
0x101d  call     string Microsoft.ReportingServices.Diagnostics.Canonicalization::GetRBFilePath(string file, string subdir, bool deployExtension)
0x1022  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1027  pop
0x1028  ldloc.s  4
0x102a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x102f  brtrue.s loc_FF2
0x1031  leave.s  loc_1048
0x1033  ldloc.s  4
0x1035  isinst   [mscorlib]System.IDisposable
0x103a  stloc.s  6
0x103c  ldloc.s  6
0x103e  brfalse.s loc_1047
0x1040  ldloc.s  6
0x1042  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1047  endfinally
0x1048  ldloc.2
0x1049  ldsfld   string Microsoft.ReportingServices.Diagnostics.Canonicalization::XPathFile
0x104e  ldloc.1
0x104f  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x1054  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1059  stloc.s  4
0x105b  br.s     loc_1093
0x105d  ldloc.s  4
0x105f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1064  castclass [System.Xml]System.Xml.XmlNode
0x1069  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x106e  ldstr    aName// "name"
0x1073  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1078  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x107d  stloc.s  7
0x107f  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.Diagnostics.Canonicalization::m_reportbuilderFiles
0x1084  ldloc.s  7
0x1086  ldarg.1
0x1087  ldc.i4.1
0x1088  call     string Microsoft.ReportingServices.Diagnostics.Canonicalization::GetRBFilePath(string file, string subdir, bool deployExtension)
0x108d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1092  pop
0x1093  ldloc.s  4
0x1095  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x109a  brtrue.s loc_105D
0x109c  leave.s  loc_10B3
0x109e  ldloc.s  4
0x10a0  isinst   [mscorlib]System.IDisposable
0x10a5  stloc.s  6
0x10a7  ldloc.s  6
0x10a9  brfalse.s loc_10B2
0x10ab  ldloc.s  6
0x10ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10b2  endfinally
0x10b3  leave.s  loc_10EA
0x10b5  stloc.s  8
0x10b7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_HttpRuntimeTracer()
0x10bc  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x10c1  brfalse.s loc_10E7
0x10c3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_HttpRuntimeTracer()
0x10c8  ldc.i4.1
0x10c9  ldstr    aAddfilesinmani// "AddFilesInManifest: unexpected exceptio"...
0x10ce  ldc.i4.2
0x10cf  newarr   [mscorlib]System.Object
0x10d4  dup
0x10d5  ldc.i4.0
0x10d6  ldarg.0
0x10d7  stelem.ref
0x10d8  dup
0x10d9  ldc.i4.1
0x10da  ldloc.s  8
0x10dc  callvirt instance string [mscorlib]System.Object::ToString()
0x10e1  stelem.ref
0x10e2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x10e7  ldloc.s  8
0x10e9  throw
0x10ea  ret
```
