# Microsoft.Reporting.WebForms.WebRequestHelper::ExceptionFromWebResponseUnwrapped

- ea: `0x22db0`
- end: `0x22e9b`
- name: `Microsoft.Reporting.WebForms.WebRequestHelper::ExceptionFromWebResponseUnwrapped`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x22da0`

## callees

- `0x2f30`
- `0x22db0`

## string_xrefs

- `0x22e53`: `http://www.microsoft.com/sql/reportingservices`

## pseudocode

```c

```

## disassembly

```asm
0x22db0  ldarg.0
0x22db1  isinst   [mscorlib]System.IO.IOException
0x22db6  stloc.0
0x22db7  ldarg.0
0x22db8  isinst   [System]System.Net.WebException
0x22dbd  stloc.1
0x22dbe  ldloc.0
0x22dbf  brfalse.s loc_22DE9
0x22dc1  ldloc.0
0x22dc2  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x22dc7  isinst   [System]System.Net.Sockets.SocketException
0x22dcc  stloc.2
0x22dcd  ldloc.2
0x22dce  brfalse  loc_22E96
0x22dd3  ldloc.2
0x22dd4  callvirt instance valuetype [System]System.Net.Sockets.SocketError [System]System.Net.Sockets.SocketException::get_SocketErrorCode()
0x22dd9  ldc.i4   0x2714
0x22dde  bne.un   loc_22E96
0x22de3  newobj   instance void [mscorlib]System.OperationCanceledException::.ctor()
0x22de8  ret
0x22de9  ldloc.1
0x22dea  brfalse  loc_22E96
0x22def  ldloc.1
0x22df0  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x22df5  ldc.i4.6
0x22df6  bne.un.s loc_22DFE
0x22df8  newobj   instance void [mscorlib]System.OperationCanceledException::.ctor()
0x22dfd  ret
0x22dfe  ldloc.1
0x22dff  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x22e04  brfalse  loc_22E96
0x22e09  ldloc.1
0x22e0a  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x22e0f  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x22e14  stloc.3
0x22e15  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x22e1a  stloc.s  4
0x22e1c  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x22e21  stloc.s  5
0x22e23  ldloc.s  5
0x22e25  ldc.i4.0
0x22e26  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_CheckCharacters(bool)
0x22e2b  ldloc.3
0x22e2c  ldloc.s  5
0x22e2e  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlReaderSettings)
0x22e33  stloc.s  6
0x22e35  ldloc.s  4
0x22e37  ldloc.s  6
0x22e39  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x22e3e  ldloc.s  4
0x22e40  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x22e45  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x22e4a  stloc.s  7
0x22e4c  ldloc.s  7
0x22e4e  ldstr    aRs// "rs"
0x22e53  ldstr    aHttpWwwMicroso// "http://www.microsoft.com/sql/reportings"...
0x22e58  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x22e5d  ldloc.s  4
0x22e5f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x22e64  brfalse.s loc_22E8A
0x22e66  ldloc.s  4
0x22e68  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x22e6d  ldstr    aRsMoreinformat// "rs:MoreInformation"
0x22e72  ldloc.s  7
0x22e74  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x22e79  call     class Microsoft.Reporting.WebForms.ReportServerException Microsoft.Reporting.WebForms.ReportServerException::FromMoreInformationNode(class [System.Xml]System.Xml.XmlNode moreInfoNode)
0x22e7e  stloc.s  8
0x22e80  ldloc.s  8
0x22e82  brfalse.s loc_22E8A
0x22e84  ldloc.s  8
0x22e86  stloc.s  9
0x22e88  leave.s  loc_22E98
0x22e8a  leave.s  loc_22E96
0x22e8c  pop
0x22e8d  leave.s  loc_22E96
0x22e8f  ldloc.3
0x22e90  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x22e95  endfinally
0x22e96  ldarg.0
0x22e97  ret
0x22e98  ldloc.s  9
0x22e9a  ret
```
