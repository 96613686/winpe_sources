# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseDataExtensions

- ea: `0x5b60`
- end: `0x5bc2`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseDataExtensions`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5bd0`

## callees

- `0x5030`
- `0x5100`
- `0x5b60`
- `0x5cf0`
- `0x5d40`

## pseudocode

```c

```

## disassembly

```asm
0x5b60  ldarg.1
0x5b61  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x5b66  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5b6b  stloc.0
0x5b6c  br.s     loc_5BA6
0x5b6e  ldloc.0
0x5b6f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b74  castclass [System.Xml]System.Xml.XmlNode
0x5b79  stloc.1
0x5b7a  ldloc.1
0x5b7b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x5b80  ldc.i4.8
0x5b81  beq.s    loc_5BA6
0x5b83  newobj   instance void Microsoft.ReportingServices.Diagnostics.Extension::.ctor()
0x5b88  stloc.2
0x5b89  ldloc.2
0x5b8a  ldarg.1
0x5b8b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5b90  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x5b95  ldarg.0
0x5b96  ldloc.1
0x5b97  ldloca.s 2
0x5b99  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension)
0x5b9e  ldarg.0
0x5b9f  ldloc.2
0x5ba0  ldarg.2
0x5ba1  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray(class Microsoft.ReportingServices.Diagnostics.Extension extension, class ExtensionArray array)
0x5ba6  ldloc.0
0x5ba7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5bac  brtrue.s loc_5B6E
0x5bae  leave.s  loc_5BC1
0x5bb0  ldloc.0
0x5bb1  isinst   [mscorlib]System.IDisposable
0x5bb6  stloc.3
0x5bb7  ldloc.3
0x5bb8  brfalse.s loc_5BC0
0x5bba  ldloc.3
0x5bbb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5bc0  endfinally
0x5bc1  ret
```
