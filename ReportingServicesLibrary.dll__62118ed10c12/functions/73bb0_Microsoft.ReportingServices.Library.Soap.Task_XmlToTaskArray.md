# Microsoft.ReportingServices.Library.Soap.Task::XmlToTaskArray

- ea: `0x73bb0`
- end: `0x73c74`
- name: `Microsoft.ReportingServices.Library.Soap.Task::XmlToTaskArray`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3d030`
- `0x3d610`

## callees

- `0x73bb0`

## string_xrefs

- `0x73c1a`: `TaskID`
- `0x73bc1`: `/Tasks/Task`

## pseudocode

```c

```

## disassembly

```asm
0x73bb0  ldarg.0
0x73bb1  brtrue.s loc_73BB5
0x73bb3  ldnull
0x73bb4  ret
0x73bb5  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x73bba  dup
0x73bbb  ldarg.0
0x73bbc  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentString(class [System.Xml]System.Xml.XmlDocument, string)
0x73bc1  ldstr    aTasksTask// "/Tasks/Task"
0x73bc6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x73bcb  stloc.0
0x73bcc  ldloc.0
0x73bcd  brtrue.s loc_73BD1
0x73bcf  ldnull
0x73bd0  ret
0x73bd1  ldloc.0
0x73bd2  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x73bd7  newarr   [mscorlib]System.String
0x73bdc  stloc.1
0x73bdd  ldc.i4.0
0x73bde  stloc.2
0x73bdf  ldloc.0
0x73be0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x73be5  stloc.3
0x73be6  br.s     loc_73C54
0x73be8  ldloc.3
0x73be9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x73bee  castclass [System.Xml]System.Xml.XmlNode
0x73bf3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x73bf8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x73bfd  stloc.s  4
0x73bff  br.s     loc_73C30
0x73c01  ldloc.s  4
0x73c03  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x73c08  castclass [System.Xml]System.Xml.XmlNode
0x73c0d  stloc.s  5
0x73c0f  ldloc.s  5
0x73c11  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x73c16  stloc.s  6
0x73c18  ldloc.s  6
0x73c1a  ldstr    aTaskid// "TaskID"
0x73c1f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x73c24  brfalse.s loc_73C30
0x73c26  ldloc.1
0x73c27  ldloc.2
0x73c28  ldloc.s  5
0x73c2a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x73c2f  stelem.ref
0x73c30  ldloc.s  4
0x73c32  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x73c37  brtrue.s loc_73C01
0x73c39  leave.s  loc_73C50
0x73c3b  ldloc.s  4
0x73c3d  isinst   [mscorlib]System.IDisposable
0x73c42  stloc.s  7
0x73c44  ldloc.s  7
0x73c46  brfalse.s loc_73C4F
0x73c48  ldloc.s  7
0x73c4a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x73c4f  endfinally
0x73c50  ldloc.2
0x73c51  ldc.i4.1
0x73c52  add
0x73c53  stloc.2
0x73c54  ldloc.3
0x73c55  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x73c5a  brtrue.s loc_73BE8
0x73c5c  leave.s  loc_73C72
0x73c5e  ldloc.3
0x73c5f  isinst   [mscorlib]System.IDisposable
0x73c64  stloc.s  7
0x73c66  ldloc.s  7
0x73c68  brfalse.s loc_73C71
0x73c6a  ldloc.s  7
0x73c6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x73c71  endfinally
0x73c72  ldloc.1
0x73c73  ret
```
