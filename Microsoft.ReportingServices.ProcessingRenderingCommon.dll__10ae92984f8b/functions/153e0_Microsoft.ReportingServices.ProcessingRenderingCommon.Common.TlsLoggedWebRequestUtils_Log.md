# Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsLoggedWebRequestUtils::Log

- ea: `0x153e0`
- end: `0x153ff`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsLoggedWebRequestUtils::Log`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14230`
- `0x14f00`

## string_xrefs

- `0x153e0`: `Outbound TLS Protocol (WebRequest): {0}`

## pseudocode

```c

```

## disassembly

```asm
0x153e0  ldstr    aOutboundTlsPro// "Outbound TLS Protocol (WebRequest): {0}"
0x153e5  ldc.i4.1
0x153e6  newarr   [mscorlib]System.Object
0x153eb  dup
0x153ec  ldc.i4.0
0x153ed  ldarg.0
0x153ee  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x153f3  call     string Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetTlsProtocol(class [mscorlib]System.IO.Stream stream)
0x153f8  stelem.ref
0x153f9  call     void Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::Info(string messageFormat, object[] parameters)
0x153fe  ret
```
