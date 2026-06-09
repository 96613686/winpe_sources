# Microsoft.ReportingServices.Modeling.DsvCompareInfo::LoadXml

- ea: `0xd790`
- end: `0xd7d0`
- name: `Microsoft.ReportingServices.Modeling.DsvCompareInfo::LoadXml`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd650`

## callees

- `0xbaa0`
- `0xbb10`
- `0xd790`
- `0x2ed90`

## string_xrefs

- `0xd798`: `CompareInfo`
- `0xd7a8`: `CompareInfo`

## pseudocode

```c

```

## disassembly

```asm
0xd790  ldarg.1
0xd791  call     class [System.Xml]System.Xml.XmlReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.XmlFragmentUtil::ReadXmlString(string)
0xd796  stloc.0
0xd797  ldloc.0
0xd798  ldstr    aCompareinfo// "CompareInfo"
0xd79d  ldsfld   string [mscorlib]System.String::Empty
0xd7a2  call     void Microsoft.ReportingServices.Modeling.XmlUtil::CheckElement(class [System.Xml]System.Xml.XmlReader xr, string localName, string namespaceUri)
0xd7a7  ldloc.0
0xd7a8  ldstr    aCompareinfo// "CompareInfo"
0xd7ad  ldsfld   string [mscorlib]System.String::Empty
0xd7b2  ldarg.0
0xd7b3  ldftn    instance bool Microsoft.ReportingServices.Modeling.DsvCompareInfo::LoadXmlElement(class [System.Xml]System.Xml.XmlReader xr)
0xd7b9  newobj   instance void LoadXmlElementLDC::.ctor(object object, native int method)
0xd7be  call     void Microsoft.ReportingServices.Modeling.XmlUtil::LoadDirectChildren(class [System.Xml]System.Xml.XmlReader xr, string parentElementName, string parentElementNamespaceURI, class LoadXmlElementLDC loadXmlElement)
0xd7c3  leave.s  loc_D7CF
0xd7c5  ldloc.0
0xd7c6  brfalse.s loc_D7CE
0xd7c8  ldloc.0
0xd7c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd7ce  endfinally
0xd7cf  ret
```
