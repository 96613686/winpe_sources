# Microsoft.Windows.Diagnosis.ManagedHost::ConvertStringToXml

- ea: `0x790`
- end: `0x7e1`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::ConvertStringToXml`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x200`

## callees

- `0x790`

## pseudocode

```c

```

## disassembly

```asm
0x790  ldnull
0x791  stloc.0
0x792  ldnull
0x793  stloc.1
0x794  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x799  stloc.0
0x79a  ldloc.0
0x79b  ldloc.0
0x79c  ldstr    a10// "1.0"
0x7a1  ldstr    aUtf8// "UTF-8"
0x7a6  ldnull
0x7a7  callvirt instance class [System.Xml]System.Xml.XmlDeclaration [System.Xml]System.Xml.XmlDocument::CreateXmlDeclaration(string, string, string)
0x7ac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x7b1  pop
0x7b2  ldloc.0
0x7b3  ldarg.2
0x7b4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x7b9  stloc.1
0x7ba  ldloc.1
0x7bb  ldloc.0
0x7bc  ldarg.1
0x7bd  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x7c2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x7c7  pop
0x7c8  ldloc.0
0x7c9  ldloc.1
0x7ca  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x7cf  pop
0x7d0  leave.s  loc_7DF
0x7d2  pop
0x7d3  ldc.i4   0x803C0103
0x7d8  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x7dd  leave.s  loc_7DF
0x7df  ldloc.0
0x7e0  ret
```
