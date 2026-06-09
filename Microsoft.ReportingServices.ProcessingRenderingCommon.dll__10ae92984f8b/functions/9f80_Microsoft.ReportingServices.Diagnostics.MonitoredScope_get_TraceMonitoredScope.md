# Microsoft.ReportingServices.Diagnostics.MonitoredScope::get_TraceMonitoredScope

- ea: `0x9f80`
- end: `0x9fe9`
- name: `Microsoft.ReportingServices.Diagnostics.MonitoredScope::get_TraceMonitoredScope`
- size: `105`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa010`
- `0xa040`
- `0xa060`
- `0xa080`
- `0xa0b0`
- `0xa0e0`
- `0xa120`
- `0xa180`

## callees

- `0x9f80`

## pseudocode

```c

```

## disassembly

```asm
0x9f80  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Diagnostics.MonitoredScope::traceMonitoredScope
0x9f85  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x9f8a  brtrue.s loc_9FDE
0x9f8c  ldc.i4.0
0x9f8d  stloc.0
0x9f8e  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x9f93  ldstr    aSoftwareMicros// "Software\\Microsoft\\ReportServerTracin"...
0x9f98  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x9f9d  stloc.1
0x9f9e  ldloc.1
0x9f9f  brfalse.s loc_9FC2
0x9fa1  ldloc.1
0x9fa2  ldstr    aTracemonitored// "TraceMonitoredScope"
0x9fa7  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x9fac  stloc.2
0x9fad  ldloc.2
0x9fae  isinst   [mscorlib]System.Int32
0x9fb3  brfalse.s loc_9FC0
0x9fb5  ldloc.2
0x9fb6  unbox.any [mscorlib]System.Int32
0x9fbb  ldc.i4.1
0x9fbc  ceq
0x9fbe  br.s     loc_9FC1
0x9fc0  ldc.i4.0
0x9fc1  stloc.0
0x9fc2  leave.s  loc_9FCE
0x9fc4  ldloc.1
0x9fc5  brfalse.s loc_9FCD
0x9fc7  ldloc.1
0x9fc8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9fcd  endfinally
0x9fce  leave.s  loc_9FD3
0x9fd0  pop
0x9fd1  leave.s  loc_9FD3
0x9fd3  ldloc.0
0x9fd4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x9fd9  stsfld   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Diagnostics.MonitoredScope::traceMonitoredScope
0x9fde  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Diagnostics.MonitoredScope::traceMonitoredScope
0x9fe3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x9fe8  ret
```
