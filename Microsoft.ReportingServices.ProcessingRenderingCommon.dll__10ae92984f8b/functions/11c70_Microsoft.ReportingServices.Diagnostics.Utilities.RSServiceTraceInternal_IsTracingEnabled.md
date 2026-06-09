# Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::IsTracingEnabled

- ea: `0x11c70`
- end: `0x11c8b`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::IsTracingEnabled`
- size: `27`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11980`
- `0x119a0`
- `0x119c0`
- `0x119e0`
- `0x11a10`
- `0x11a40`
- `0x11d40`

## callees

- `0x11840`

## pseudocode

```c

```

## disassembly

```asm
0x11c70  ldarg.0
0x11c71  ldarg.2
0x11c72  ldarg.0
0x11c73  ldflda   valuetype [System]System.Diagnostics.TraceLevel Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_traceLevel
0x11c78  callvirt instance bool Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::GetTraceLevel(string componentName, [out] valuetype [System]System.Diagnostics.TraceLevel& componentLevel)
0x11c7d  pop
0x11c7e  ldarg.1
0x11c7f  ldarg.0
0x11c80  ldfld    valuetype [System]System.Diagnostics.TraceLevel Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_traceLevel
0x11c85  cgt
0x11c87  ldc.i4.0
0x11c88  ceq
0x11c8a  ret
```
