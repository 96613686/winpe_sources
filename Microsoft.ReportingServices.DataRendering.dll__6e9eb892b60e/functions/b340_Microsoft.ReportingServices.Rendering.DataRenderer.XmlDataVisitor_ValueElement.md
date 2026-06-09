# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::ValueElement

- ea: `0xb340`
- end: `0xb37a`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::ValueElement`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb3a0`

## callees

- `0xa2f0`
- `0xa570`
- `0xb340`
- `0xb440`

## pseudocode

```c

```

## disassembly

```asm
0xb340  ldarg.s  4
0xb342  brfalse.s loc_B34C
0xb344  ldarg.0
0xb345  ldarga.s 1
0xb347  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::ValidateElement(string& name)
0xb34c  ldarg.2
0xb34d  brfalse.s loc_B379
0xb34f  ldarg.0
0xb350  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xb355  ldarg.1
0xb356  ldarg.0
0xb357  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::m_schemaName
0xb35c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb361  ldarg.0
0xb362  ldarg.0
0xb363  ldarg.2
0xb364  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::XmlConvertOriginalValue(object val)
0xb369  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteString(string text)
0xb36e  ldarg.0
0xb36f  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xb374  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb379  ret
```
