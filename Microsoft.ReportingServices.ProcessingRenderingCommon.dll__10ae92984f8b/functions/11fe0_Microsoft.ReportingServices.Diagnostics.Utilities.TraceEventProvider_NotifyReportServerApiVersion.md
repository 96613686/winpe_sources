# Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyReportServerApiVersion

- ea: `0x11fe0`
- end: `0x12003`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyReportServerApiVersion`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11fe6`: `PowerView API: Command={0}, GroupVersion={1}, Api-Version={2}`

## pseudocode

```c

```

## disassembly

```asm
0x11fe0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x11fe5  ldc.i4.3
0x11fe6  ldstr    aPowerviewApiCo// "PowerView API: Command={0}, GroupVersio"...
0x11feb  ldc.i4.3
0x11fec  newarr   [mscorlib]System.Object
0x11ff1  dup
0x11ff2  ldc.i4.0
0x11ff3  ldarg.1
0x11ff4  stelem.ref
0x11ff5  dup
0x11ff6  ldc.i4.1
0x11ff7  ldarg.2
0x11ff8  stelem.ref
0x11ff9  dup
0x11ffa  ldc.i4.2
0x11ffb  ldarg.3
0x11ffc  stelem.ref
0x11ffd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x12002  ret
```
