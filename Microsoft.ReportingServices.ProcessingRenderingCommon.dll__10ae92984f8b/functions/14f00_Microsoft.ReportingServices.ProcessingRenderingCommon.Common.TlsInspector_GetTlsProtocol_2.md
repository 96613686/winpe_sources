# Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetTlsProtocol_2

- ea: `0x14f00`
- end: `0x14f47`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetTlsProtocol_2`
- size: `71`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14e90`
- `0x14eb0`
- `0x153e0`

## callees

- `0x142a0`
- `0x14f00`

## string_xrefs

- `0x14f2d`: `Error retrieving SSL protocol from http response message. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x14f00  ldarg.0
0x14f01  brtrue.s loc_14F0B
0x14f03  ldstr    aNocontent// "NoContent"
0x14f08  stloc.1
0x14f09  leave.s  loc_14F45
0x14f0b  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IO.Stream, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::streamProtocolGetter
0x14f10  ldarg.0
0x14f11  callvirt instance var<u1> class [mscorlib]System.Func`2<class [mscorlib]System.IO.Stream, object>::Invoke(void)
0x14f16  unbox.any [System]System.Security.Authentication.SslProtocols
0x14f1b  stloc.0
0x14f1c  ldloca.s 0
0x14f1e  constrained. [System]System.Security.Authentication.SslProtocols
0x14f24  callvirt instance string [mscorlib]System.Object::ToString()
0x14f29  stloc.1
0x14f2a  leave.s  loc_14F45
0x14f2c  stloc.2
0x14f2d  ldstr    aErrorRetrievin// "Error retrieving SSL protocol from http"...
0x14f32  ldloc.2
0x14f33  call     string [mscorlib]System.String::Format(string, object)
0x14f38  call     void Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::Error(string message)
0x14f3d  ldstr    aTlsdiscoveryer// "TlsDiscoveryError"
0x14f42  stloc.1
0x14f43  leave.s  loc_14F45
0x14f45  ldloc.1
0x14f46  ret
```
