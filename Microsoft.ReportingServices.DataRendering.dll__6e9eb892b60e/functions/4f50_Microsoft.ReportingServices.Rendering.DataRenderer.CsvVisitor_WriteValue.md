# Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue

- ea: `0x4f50`
- end: `0x4f84`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue`
- size: `52`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4070`
- `0x40d0`
- `0x4260`
- `0x4290`
- `0x42e0`
- `0x4330`
- `0x43a0`
- `0x4450`
- `0x44a0`
- `0x4760`
- `0x47f0`
- `0x4890`
- `0x48e0`
- `0x4930`

## callees

- `0x4f50`
- `0x4f90`

## pseudocode

```c

```

## disassembly

```asm
0x4f50  ldarg.0
0x4f51  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::m_atRowStart
0x4f56  brtrue.s loc_4F69
0x4f58  ldarg.0
0x4f59  ldfld    class [mscorlib]System.IO.StreamWriter Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::m_writer
0x4f5e  ldarg.0
0x4f5f  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::m_fieldDelimiter
0x4f64  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x4f69  ldarg.0
0x4f6a  ldc.i4.0
0x4f6b  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::m_atRowStart
0x4f70  ldarg.0
0x4f71  ldfld    class [mscorlib]System.IO.StreamWriter Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::m_writer
0x4f76  ldarg.0
0x4f77  ldarg.1
0x4f78  ldarg.2
0x4f79  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::FormatValue(string value, bool excelMode)
0x4f7e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x4f83  ret
```
