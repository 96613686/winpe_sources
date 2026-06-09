# Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyAttemptRestoreSession

- ea: `0x120f0`
- end: `0x12113`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyAttemptRestoreSession`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x120f6`: `Attempt Restore Session: SessionId={0}, Reason={1}, Outcome={2}`

## pseudocode

```c

```

## disassembly

```asm
0x120f0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x120f5  ldc.i4.3
0x120f6  ldstr    aAttemptRestore// "Attempt Restore Session: SessionId={0},"...
0x120fb  ldc.i4.3
0x120fc  newarr   [mscorlib]System.Object
0x12101  dup
0x12102  ldc.i4.0
0x12103  ldarg.1
0x12104  stelem.ref
0x12105  dup
0x12106  ldc.i4.1
0x12107  ldarg.2
0x12108  stelem.ref
0x12109  dup
0x1210a  ldc.i4.2
0x1210b  ldarg.3
0x1210c  stelem.ref
0x1210d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x12112  ret
```
