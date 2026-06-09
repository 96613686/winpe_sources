# Microsoft.ReportingServices.ProcessingRenderingCommon.Common.HttpApi::GetTlsProtocolInfo

- ea: `0x15320`
- end: `0x153d0`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Common.HttpApi::GetTlsProtocolInfo`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14e30`

## callees

- `0x14270`
- `0x15320`

## string_xrefs

- `0x153af`: `Error occcured while getting the SSL protocol information from the request : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15320  ldarg.0
0x15321  brfalse  loc_153C2
0x15326  ldarg.0
0x15327  dup
0x15328  stloc.1
0x15329  brfalse.s loc_15330
0x1532b  ldloc.1
0x1532c  ldlen
0x1532d  conv.i4
0x1532e  brtrue.s loc_15335
0x15330  ldc.i4.0
0x15331  conv.u
0x15332  stloc.0
0x15333  br.s     loc_1533E
0x15335  ldloc.1
0x15336  ldc.i4.0
0x15337  ldelema  [mscorlib]System.Byte
0x1533c  conv.u
0x1533d  stloc.0
0x1533e  ldloc.0
0x1533f  stloc.2
0x15340  ldloc.0
0x15341  ldarg.1
0x15342  call     void* [mscorlib]System.IntPtr::op_Explicit(native int)
0x15347  sub
0x15348  ldc.i4.1
0x15349  div
0x1534a  conv.i8
0x1534b  stloc.3
0x1534c  ldc.i4.0
0x1534d  stloc.s  4
0x1534f  br.s     loc_1539C
0x15351  ldloc.3
0x15352  conv.i
0x15353  ldloc.2
0x15354  ldfld    valuetype HTTP_REQUEST_INFO* HTTP_REQUEST_V2::pRequestInfo
0x15359  ldloc.s  4
0x1535b  conv.i
0x1535c  sizeof   HTTP_REQUEST_INFO
0x15362  mul
0x15363  add
0x15364  conv.u
0x15365  add
0x15366  stloc.s  5
0x15368  ldloc.s  5
0x1536a  ldc.i4.0
0x1536b  conv.u
0x1536c  beq.s    loc_15396
0x1536e  ldloc.s  5
0x15370  ldfld    void* HTTP_REQUEST_INFO::pInfo
0x15375  ldc.i4.0
0x15376  conv.u
0x15377  beq.s    loc_15396
0x15379  ldloc.s  5
0x1537b  ldfld    valuetype HTTP_REQUEST_INFO_TYPE HTTP_REQUEST_INFO::InfoType
0x15380  ldc.i4.2
0x15381  bne.un.s loc_15396
0x15383  ldloc.3
0x15384  conv.i
0x15385  ldloc.s  5
0x15387  ldfld    void* HTTP_REQUEST_INFO::pInfo
0x1538c  add
0x1538d  ldobj    HTTP_SSL_PROTOCOL_INFO
0x15392  stloc.s  6
0x15394  leave.s  loc_153CD
0x15396  ldloc.s  4
0x15398  ldc.i4.1
0x15399  add
0x1539a  stloc.s  4
0x1539c  ldloc.s  4
0x1539e  ldloc.2
0x1539f  ldfld    unsigned int16 HTTP_REQUEST_V2::RequestInfoCount
0x153a4  blt.s    loc_15351
0x153a6  leave.s  loc_153AB
0x153a8  ldnull
0x153a9  stloc.1
0x153aa  endfinally
0x153ab  leave.s  loc_153C2
0x153ad  stloc.s  7
0x153af  ldstr    aErrorOcccuredW// "Error occcured while getting the SSL pr"...
0x153b4  ldloc.s  7
0x153b6  call     string [mscorlib]System.String::Format(string, object)
0x153bb  call     void Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::Warn(string message)
0x153c0  leave.s  loc_153C2
0x153c2  ldloca.s 8
0x153c4  initobj  HTTP_SSL_PROTOCOL_INFO
0x153ca  ldloc.s  8
0x153cc  ret
0x153cd  ldloc.s  6
0x153cf  ret
```
