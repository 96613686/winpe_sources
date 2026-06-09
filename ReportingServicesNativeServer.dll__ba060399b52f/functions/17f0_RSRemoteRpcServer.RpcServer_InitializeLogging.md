# RSRemoteRpcServer.RpcServer::InitializeLogging

- ea: `0x17f0`
- end: `0x1818`
- name: `RSRemoteRpcServer.RpcServer::InitializeLogging`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x13e0`
- `0x14a0`

## callees

- `0x1320`
- `0x17f0`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldc.i4.0
0x17f1  conv.i8
0x17f2  ldsfld   void* g_pNativeTracer
0x17f7  bne.un.s loc_1817
0x17f9  ldc.i4.0
0x17fa  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 ?A0x3248e70b.?loggingInitialized@?1??InitializeLogging@RpcServer@RSRemoteRpcServer@@AE$AAMXXZ@4JA
0x17ff  ldc.i4.1
0x1800  ldc.i4.0
0x1801  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0x1806  bne.un.s loc_1817
0x1808  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY0O@$$CBG ??_C@_1BM@HFMLOAJF@?$AAD?$AAe?$AAf?$AAa?$AAu?$AAl?$AAt?$AAD?$AAo?$AAm?$AAa?$AAi?$AAn@
0x180d  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void* CreateNativeLoggingObject(unsigned int16* rpcEndpointName)
0x1812  stsfld   void* g_pNativeTracer
0x1817  ret
```
