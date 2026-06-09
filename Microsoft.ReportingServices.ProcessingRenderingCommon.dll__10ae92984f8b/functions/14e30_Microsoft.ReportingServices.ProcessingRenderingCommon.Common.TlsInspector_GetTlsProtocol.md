# Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetTlsProtocol

- ea: `0x14e30`
- end: `0x14e8e`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetTlsProtocol`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x142a0`
- `0x14e30`
- `0x151b0`
- `0x151d0`
- `0x15320`
- `0x17aa0`

## string_xrefs

- `0x14e74`: `Error retrieving SSL protocol from http response message. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x14e30  ldarg.0
0x14e31  callvirt instance bool [System]System.Net.HttpListenerRequest::get_IsSecureConnection()
0x14e36  brtrue.s loc_14E4F
0x14e38  ldarg.0
0x14e39  callvirt instance class [System]System.Uri [System]System.Net.HttpListenerRequest::get_Url()
0x14e3e  callvirt instance string [System]System.Uri::get_Scheme()
0x14e43  ldsfld   string [System]System.Uri::UriSchemeHttps
0x14e48  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e4d  brfalse.s loc_14E6B
0x14e4f  ldarg.0
0x14e50  call     unsigned int8[] Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetRequestBuffer(class [System]System.Net.HttpListenerRequest httpListenerRequest)
0x14e55  ldarg.0
0x14e56  call     native int Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetOriginalBlobAddress(class [System]System.Net.HttpListenerRequest httpListenerRequest)
0x14e5b  call     valuetype HTTP_SSL_PROTOCOL_INFO Microsoft.ReportingServices.ProcessingRenderingCommon.Common.HttpApi::GetTlsProtocolInfo(unsigned int8[] memoryBlob, native int originalAddress)
0x14e60  stloc.0
0x14e61  ldloca.s 0
0x14e63  call     instance string HTTP_SSL_PROTOCOL_INFO::ProtocolName()
0x14e68  stloc.1
0x14e69  leave.s  loc_14E8C
0x14e6b  ldstr    aUnknowntls// "UnknownTLS"
0x14e70  stloc.1
0x14e71  leave.s  loc_14E8C
0x14e73  stloc.2
0x14e74  ldstr    aErrorRetrievin// "Error retrieving SSL protocol from http"...
0x14e79  ldloc.2
0x14e7a  call     string [mscorlib]System.String::Format(string, object)
0x14e7f  call     void Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::Error(string message)
0x14e84  ldstr    aTlsdiscoveryer// "TlsDiscoveryError"
0x14e89  stloc.1
0x14e8a  leave.s  loc_14E8C
0x14e8c  ldloc.1
0x14e8d  ret
```
