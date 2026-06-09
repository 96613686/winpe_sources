# Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::get_InternalTrace

- ea: `0x14100`
- end: `0x14146`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::get_InternalTrace`
- size: `70`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14190`
- `0x141a0`
- `0x141b0`
- `0x141c0`
- `0x141d0`
- `0x141e0`
- `0x141f0`
- `0x14200`
- `0x14210`
- `0x14220`
- `0x14230`
- `0x14240`
- `0x14250`
- `0x14260`
- `0x14270`
- `0x14280`
- `0x14290`
- `0x142a0`
- `0x142b0`
- `0x142c0`
- `0x142d0`

## callees

- `0x14100`
- `0x14370`

## pseudocode

```c

```

## disassembly

```asm
0x14100  volatile.
0x14102  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.IEngineTracerDestination Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::_traceDestination
0x14107  stloc.0
0x14108  ldloc.0
0x14109  brtrue.s loc_14144
0x1410b  ldsfld   object Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::_tracerWLock
0x14110  stloc.1
0x14111  ldc.i4.0
0x14112  stloc.2
0x14113  ldloc.1
0x14114  ldloca.s 2
0x14116  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1411b  volatile.
0x1411d  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.IEngineTracerDestination Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::_traceDestination
0x14122  brtrue.s loc_14130
0x14124  newobj   instance void Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.NullTracerDestination::.ctor()
0x14129  volatile.
0x1412b  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.IEngineTracerDestination Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::_traceDestination
0x14130  volatile.
0x14132  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.IEngineTracerDestination Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::_traceDestination
0x14137  stloc.0
0x14138  leave.s  loc_14144
0x1413a  ldloc.2
0x1413b  brfalse.s loc_14143
0x1413d  ldloc.1
0x1413e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x14143  endfinally
0x14144  ldloc.0
0x14145  ret
```
