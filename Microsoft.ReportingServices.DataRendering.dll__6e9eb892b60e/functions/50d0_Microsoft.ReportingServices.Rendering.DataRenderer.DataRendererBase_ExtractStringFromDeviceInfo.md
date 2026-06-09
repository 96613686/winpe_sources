# Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo

- ea: `0x50d0`
- end: `0x5116`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo`
- size: `70`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c70`
- `0x1cd0`
- `0x4c10`
- `0x7c80`

## callees

- `0x50d0`

## pseudocode

```c

```

## disassembly

```asm
0x50d0  ldnull
0x50d1  stloc.0
0x50d2  ldarg.1
0x50d3  brfalse.s loc_50DD
0x50d5  ldarg.2
0x50d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x50db  brfalse.s loc_50DF
0x50dd  ldloc.0
0x50de  ret
0x50df  nop
0x50e0  ldarg.1
0x50e1  ldarg.2
0x50e2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x50e7  stloc.0
0x50e8  leave.s  loc_5114
0x50ea  stloc.1
0x50eb  ldloc.1
0x50ec  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Common.AsynchronousExceptionDetection::IsStoppingException(class [mscorlib]System.Exception)
0x50f1  brfalse.s loc_50F5
0x50f3  rethrow
0x50f5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x50fa  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x50ff  brfalse.s loc_5112
0x5101  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x5106  ldc.i4.1
0x5107  ldloc.1
0x5108  callvirt instance string [mscorlib]System.Object::ToString()
0x510d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5112  leave.s  loc_5114
0x5114  ldloc.0
0x5115  ret
```
