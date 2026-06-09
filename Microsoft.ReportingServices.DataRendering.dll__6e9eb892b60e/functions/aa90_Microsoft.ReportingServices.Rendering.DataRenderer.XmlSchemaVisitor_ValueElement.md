# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::ValueElement

- ea: `0xaa90`
- end: `0xaaa7`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::ValueElement`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xaac0`

## callees

- `0xab80`
- `0xac00`
- `0xadf0`

## pseudocode

```c

```

## disassembly

```asm
0xaa90  ldarg.0
0xaa91  ldarg.1
0xaa92  ldc.i4.0
0xaa93  ldc.i4.1
0xaa94  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartElementDeclaration(string name, valuetype Cardinality minOccurs, valuetype Cardinality maxOccurs)
0xaa99  ldarg.0
0xaa9a  ldarg.3
0xaa9b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::WriteXmlType(valuetype [mscorlib]System.TypeCode tc)
0xaaa0  ldarg.0
0xaaa1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::EndElementDeclaration()
0xaaa6  ret
```
