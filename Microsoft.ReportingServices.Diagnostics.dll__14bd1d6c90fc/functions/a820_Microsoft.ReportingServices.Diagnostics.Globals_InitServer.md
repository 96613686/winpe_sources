# Microsoft.ReportingServices.Diagnostics.Globals::InitServer

- ea: `0xa820`
- end: `0xa84d`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::InitServer`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x94a0`
- `0x94b0`
- `0xa820`
- `0xa8e0`

## pseudocode

```c

```

## disassembly

```asm
0xa820  ldsfld   object Microsoft.ReportingServices.Diagnostics.Globals::StaticLock
0xa825  stloc.0
0xa826  ldc.i4.0
0xa827  stloc.1
0xa828  ldloc.0
0xa829  ldloca.s 1
0xa82b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa830  ldarg.0
0xa831  call     void Microsoft.ReportingServices.Diagnostics.Globals::InitServerWithoutDumperInner(bool resetAllPerfCounters)
0xa836  call     class Microsoft.ReportingServices.Diagnostics.Dumper Microsoft.ReportingServices.Diagnostics.Dumper::get_Current()
0xa83b  callvirt instance void Microsoft.ReportingServices.Diagnostics.Dumper::Init()
0xa840  leave.s  loc_A84C
0xa842  ldloc.1
0xa843  brfalse.s loc_A84B
0xa845  ldloc.0
0xa846  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa84b  endfinally
0xa84c  ret
```
