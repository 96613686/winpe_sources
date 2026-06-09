# Microsoft.ReportingServices.Library.QueuePollWorker::Stop

- ea: `0x1ea0`
- end: `0x1ef3`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::Stop`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1130`
- `0x11b0`
- `0x1690`
- `0x1ea0`
- `0x1f10`

## pseudocode

```c

```

## disassembly

```asm
0x1ea0  ldarg.0
0x1ea1  ldarg.1
0x1ea2  call     instance void Microsoft.ReportingServices.Library.PollWorker::Stop(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals/ServiceStopMode mode)
0x1ea7  ldarg.1
0x1ea8  brtrue.s loc_1EB7
0x1eaa  ldarg.0
0x1eab  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::ResetItemRows()
0x1eb0  ldarg.0
0x1eb1  ldc.i4.1
0x1eb2  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::Dispose(bool disposing)
0x1eb7  leave.s  loc_1EF2
0x1eb9  stloc.0
0x1eba  ldarg.0
0x1ebb  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1ec0  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1ec5  brfalse.s loc_1EF0
0x1ec7  ldarg.0
0x1ec8  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1ecd  ldc.i4.1
0x1ece  ldstr    aErrorStoppingQ// "Error stopping Queue worker {0}: {1}"
0x1ed3  ldc.i4.2
0x1ed4  newarr   [mscorlib]System.Object
0x1ed9  dup
0x1eda  ldc.i4.0
0x1edb  ldarg.0
0x1edc  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x1ee1  stelem.ref
0x1ee2  dup
0x1ee3  ldc.i4.1
0x1ee4  ldloc.0
0x1ee5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1eea  stelem.ref
0x1eeb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1ef0  leave.s  loc_1EF2
0x1ef2  ret
```
