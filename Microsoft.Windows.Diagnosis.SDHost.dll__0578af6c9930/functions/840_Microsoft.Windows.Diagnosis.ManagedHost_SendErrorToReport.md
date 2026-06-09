# Microsoft.Windows.Diagnosis.ManagedHost::SendErrorToReport

- ea: `0x840`
- end: `0x8a8`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::SendErrorToReport`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x200`

## callees

- `0x840`

## pseudocode

```c

```

## disassembly

```asm
0x840  ldnull
0x841  stloc.0
0x842  ldnull
0x843  stloc.1
0x844  ldnull
0x845  stloc.2
0x846  ldnull
0x847  stloc.3
0x848  ldnull
0x849  stloc.s  4
0x84b  ldarg.1
0x84c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x851  stloc.s  4
0x853  ldstr    aDebug// "Debug"
0x858  stloc.2
0x859  ldarg.2
0x85a  stloc.3
0x85b  ldarg.0
0x85c  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.Diagnosis.ManagedHost::m_ResourceManager
0x861  ldstr    aErrorrecordnam// "ErrorRecordName"
0x866  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x86b  stloc.0
0x86c  ldarg.0
0x86d  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.Diagnosis.ManagedHost::m_ResourceManager
0x872  ldstr    aErrorrecorddes// "ErrorRecordDescription"
0x877  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x87c  stloc.1
0x87d  ldarg.0
0x87e  ldfld    class [Microsoft.Windows.Diagnosis.SDCommon]Microsoft.Windows.Diagnosis.IScriptedDiagnosticInteraction Microsoft.Windows.Diagnosis.ManagedHost::m_Engine
0x883  ldloc.3
0x884  ldloc.0
0x885  ldloc.1
0x886  ldloc.s  4
0x888  ldloc.2
0x889  ldstr    asc_90DC// ""
0x88e  ldstr    asc_90DC// ""
0x893  callvirt instance void [Microsoft.Windows.Diagnosis.SDCommon]Microsoft.Windows.Diagnosis.IScriptedDiagnosticInteraction::AddXmlToReport(string, string, string, string, string, string, string)
0x898  leave.s  loc_8A7
0x89a  pop
0x89b  ldc.i4   0x803C0103
0x8a0  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x8a5  leave.s  loc_8A7
0x8a7  ret
```
