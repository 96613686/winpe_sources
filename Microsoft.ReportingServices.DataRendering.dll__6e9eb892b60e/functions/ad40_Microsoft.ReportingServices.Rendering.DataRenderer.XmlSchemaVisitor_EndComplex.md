# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::EndComplex

- ea: `0xad40`
- end: `0xad74`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::EndComplex`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xac00`

## callees

- `0xa440`
- `0xac50`
- `0xad40`

## pseudocode

```c

```

## disassembly

```asm
0xad40  ldarg.0
0xad41  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_elementLevel
0xad46  ldarg.0
0xad47  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_complexTypeLevel
0xad4c  bne.un.s loc_AD73
0xad4e  ldarg.0
0xad4f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::WriteAttributes()
0xad54  ldarg.0
0xad55  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xad5a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xad5f  ldarg.0
0xad60  ldarg.0
0xad61  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_complexTypeLevel
0xad66  ldc.i4.1
0xad67  sub
0xad68  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_complexTypeLevel
0xad6d  ldarg.0
0xad6e  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::PopScope()
0xad73  ret
```
