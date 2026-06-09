# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseRenderExtensions

- ea: `0x57d0`
- end: `0x5847`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseRenderExtensions`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5bd0`

## callees

- `0x5030`
- `0x57d0`
- `0x5850`
- `0x5920`
- `0x5cf0`
- `0x5d40`
- `0x6330`

## pseudocode

```c

```

## disassembly

```asm
0x57d0  ldarg.1
0x57d1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x57d6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x57db  stloc.0
0x57dc  br.s     loc_5828
0x57de  ldloc.0
0x57df  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x57e4  castclass [System.Xml]System.Xml.XmlNode
0x57e9  stloc.1
0x57ea  ldloc.1
0x57eb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x57f0  ldc.i4.8
0x57f1  beq.s    loc_5828
0x57f3  newobj   instance void Microsoft.ReportingServices.Diagnostics.RenderingExtension::.ctor()
0x57f8  stloc.2
0x57f9  ldloc.2
0x57fa  ldarg.1
0x57fb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5800  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x5805  ldloc.2
0x5806  stloc.3
0x5807  ldarg.0
0x5808  ldloc.1
0x5809  ldloca.s 3
0x580b  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension)
0x5810  ldarg.0
0x5811  ldloc.1
0x5812  ldloc.2
0x5813  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ExtractRenderingExternsionOverrideNames(class [System.Xml]System.Xml.XmlNode extensionElement, class Microsoft.ReportingServices.Diagnostics.RenderingExtension p)
0x5818  ldarg.0
0x5819  ldloc.1
0x581a  ldloc.2
0x581b  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ExtractRenderingExtensionDeviceInfo(class [System.Xml]System.Xml.XmlNode extensionElement, class Microsoft.ReportingServices.Diagnostics.RenderingExtension p)
0x5820  ldarg.0
0x5821  ldloc.2
0x5822  ldarg.2
0x5823  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray(class Microsoft.ReportingServices.Diagnostics.Extension extension, class ExtensionArray array)
0x5828  ldloc.0
0x5829  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x582e  brtrue.s loc_57DE
0x5830  leave.s  loc_5846
0x5832  ldloc.0
0x5833  isinst   [mscorlib]System.IDisposable
0x5838  stloc.s  4
0x583a  ldloc.s  4
0x583c  brfalse.s loc_5845
0x583e  ldloc.s  4
0x5840  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5845  endfinally
0x5846  ret
```
