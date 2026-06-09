# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::StartRootReport

- ea: `0xb240`
- end: `0xb289`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::StartRootReport`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa530`
- `0xb240`
- `0xb3f0`

## string_xrefs

- `0xb263`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xb240  ldarg.0
0xb241  ldarg.1
0xb242  ldc.i4.1
0xb243  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::InternalStartElement(string name, bool firstInstance)
0xb248  ldarg.0
0xb249  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::m_schemaName
0xb24e  brfalse.s loc_B288
0xb250  ldarg.0
0xb251  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::m_schemaLocation
0xb256  brfalse.s loc_B288
0xb258  ldarg.0
0xb259  ldstr    aXsi// "xsi"
0xb25e  ldstr    aSchemalocation// "schemaLocation"
0xb263  ldstr    aHttpWwwW3Org20_3// "http://www.w3.org/2001/XMLSchema-instan"...
0xb268  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb26d  ldstr    a01_0// "{0} {1}"
0xb272  ldarg.0
0xb273  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::m_schemaName
0xb278  ldarg.0
0xb279  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::m_schemaLocation
0xb27e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0xb283  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string prefix, string localName, string ns, string value)
0xb288  ret
```
