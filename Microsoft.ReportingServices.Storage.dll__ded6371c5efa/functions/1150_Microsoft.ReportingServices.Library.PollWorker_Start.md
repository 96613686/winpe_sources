# Microsoft.ReportingServices.Library.PollWorker::Start

- ea: `0x1150`
- end: `0x11a3`
- name: `Microsoft.ReportingServices.Library.PollWorker::Start`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb00`
- `0x1dc0`

## callees

- `0x1130`
- `0x1150`

## string_xrefs

- `0x1189`: `{0} polling service started`

## pseudocode

```c

```

## disassembly

```asm
0x1150  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1155  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_FallbackUICulture()
0x115a  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentUICulture(class [mscorlib]System.Globalization.CultureInfo)
0x115f  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1164  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1169  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x116e  ldarg.0
0x116f  ldc.i4.1
0x1170  stfld    bool Microsoft.ReportingServices.Library.PollWorker::m_continueWorking
0x1175  ldarg.0
0x1176  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.PollWorker::m_tracer
0x117b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x1180  brfalse.s loc_11A2
0x1182  ldarg.0
0x1183  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.PollWorker::m_tracer
0x1188  ldc.i4.3
0x1189  ldstr    a0PollingServic// "{0} polling service started"
0x118e  ldc.i4.1
0x118f  newarr   [mscorlib]System.Object
0x1194  dup
0x1195  ldc.i4.0
0x1196  ldarg.0
0x1197  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x119c  stelem.ref
0x119d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x11a2  ret
```
