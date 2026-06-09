# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::EndElementDeclaration

- ea: `0xac00`
- end: `0xac26`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::EndElementDeclaration`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xaa80`
- `0xaa90`

## callees

- `0xad40`
- `0xadc0`

## pseudocode

```c

```

## disassembly

```asm
0xac00  ldarg.0
0xac01  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::EndSequence()
0xac06  ldarg.0
0xac07  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::EndComplex()
0xac0c  ldarg.0
0xac0d  ldarg.0
0xac0e  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_elementLevel
0xac13  ldc.i4.1
0xac14  sub
0xac15  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_elementLevel
0xac1a  ldarg.0
0xac1b  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xac20  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xac25  ret
```
