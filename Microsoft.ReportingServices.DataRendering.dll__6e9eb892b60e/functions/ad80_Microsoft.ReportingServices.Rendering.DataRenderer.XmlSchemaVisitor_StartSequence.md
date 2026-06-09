# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartSequence

- ea: `0xad80`
- end: `0xadb7`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartSequence`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xab80`

## callees

- `0xad80`

## string_xrefs

- `0xadac`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0xad80  ldarg.0
0xad81  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_elementLevel
0xad86  ldarg.0
0xad87  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_sequenceLevel
0xad8c  beq.s    loc_ADB6
0xad8e  ldarg.0
0xad8f  ldarg.0
0xad90  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_sequenceLevel
0xad95  ldc.i4.1
0xad96  add
0xad97  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_sequenceLevel
0xad9c  ldarg.0
0xad9d  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xada2  ldstr    aXsd// "xsd"
0xada7  ldstr    aSequence// "sequence"
0xadac  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2001/XMLSchema"
0xadb1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xadb6  ret
```
