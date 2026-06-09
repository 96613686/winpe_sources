# Microsoft.ReportingServices.Library.PollWorker::Stop

- ea: `0x11b0`
- end: `0x11e5`
- name: `Microsoft.ReportingServices.Library.PollWorker::Stop`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd0`
- `0x1ea0`

## callees

- `0x1130`
- `0x11b0`

## string_xrefs

- `0x11cb`: `{0} polling service stopped`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.0
0x11b1  ldc.i4.0
0x11b2  stfld    bool Microsoft.ReportingServices.Library.PollWorker::m_continueWorking
0x11b7  ldarg.0
0x11b8  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.PollWorker::m_tracer
0x11bd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x11c2  brfalse.s loc_11E4
0x11c4  ldarg.0
0x11c5  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.PollWorker::m_tracer
0x11ca  ldc.i4.3
0x11cb  ldstr    a0PollingServic_0// "{0} polling service stopped"
0x11d0  ldc.i4.1
0x11d1  newarr   [mscorlib]System.Object
0x11d6  dup
0x11d7  ldc.i4.0
0x11d8  ldarg.0
0x11d9  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x11de  stelem.ref
0x11df  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x11e4  ret
```
