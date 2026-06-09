# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::InternalStartElement

- ea: `0xb3f0`
- end: `0xb414`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::InternalStartElement`
- size: `36`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb230`
- `0xb240`
- `0xb290`
- `0xb2a0`
- `0xb2b0`
- `0xb2c0`
- `0xb2d0`
- `0xb2e0`
- `0xb2f0`
- `0xb300`
- `0xb310`
- `0xb320`

## callees

- `0xa2f0`
- `0xa420`
- `0xb3f0`

## pseudocode

```c

```

## disassembly

```asm
0xb3f0  ldarg.2
0xb3f1  brfalse.s loc_B401
0xb3f3  ldarg.0
0xb3f4  ldarga.s 1
0xb3f6  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::ValidateElement(string& name)
0xb3fb  ldarg.0
0xb3fc  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::PushScope()
0xb401  ldarg.0
0xb402  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xb407  ldarg.1
0xb408  ldarg.0
0xb409  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::m_schemaName
0xb40e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb413  ret
```
