# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::ValueAttribute

- ea: `0xb380`
- end: `0xb39d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::ValueAttribute`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb3b0`

## callees

- `0xa3a0`
- `0xa4f0`
- `0xb380`
- `0xb440`

## pseudocode

```c

```

## disassembly

```asm
0xb380  ldarg.s  4
0xb382  brfalse.s loc_B38B
0xb384  ldarg.0
0xb385  ldarg.1
0xb386  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::ValidateAttribute(string name)
0xb38b  ldarg.2
0xb38c  brfalse.s loc_B39C
0xb38e  ldarg.0
0xb38f  ldarg.1
0xb390  ldarg.0
0xb391  ldarg.2
0xb392  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::XmlConvertOriginalValue(object val)
0xb397  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xb39c  ret
```
