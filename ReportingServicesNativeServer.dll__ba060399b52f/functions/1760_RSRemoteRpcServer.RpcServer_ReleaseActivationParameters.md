# RSRemoteRpcServer.RpcServer::ReleaseActivationParameters

- ea: `0x1760`
- end: `0x17e7`
- name: `RSRemoteRpcServer.RpcServer::ReleaseActivationParameters`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1430`

## callees

- `0x1210`
- `0x1220`
- `0x1260`
- `0x1270`
- `0x12f0`
- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0x1760  ldsfld   unsigned int16* gRpcEndpointName
0x1765  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void SysFreeString(unsigned int16* rpcEndpointName)
0x176a  ldc.i4.0
0x176b  conv.i8
0x176c  stsfld   unsigned int16* gRpcEndpointName
0x1771  ldsflda  valuetype ATL.CComQIPtr<INativeServerDelegation,&_GUID_d60fdbd8_bc6c_4ad3_8af8_4f3d6848f40e> gmpNativeDelegation
0x1776  ldc.i4.0
0x1777  conv.i8
0x1778  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool ATL.CComPtrBase<INativeServerDelegation>.!=([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtrBase<INativeServerDelegation>*, valuetype INativeServerDelegation* rpcEndpointName)
0x177d  brfalse.s loc_1789
0x177f  ldsflda  valuetype ATL.CComQIPtr<INativeServerDelegation,&_GUID_d60fdbd8_bc6c_4ad3_8af8_4f3d6848f40e> gmpNativeDelegation
0x1784  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ATL.CComPtrBase<INativeServerDelegation>.Release([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtrBase<INativeServerDelegation>*)
0x1789  ldarg.0
0x178a  ldfld    class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject RSRemoteRpcServer.RpcServer::gmpNativeDelegationObject
0x178f  stloc.2
0x1790  ldloc.2
0x1791  brfalse.s loc_17A0
0x1793  ldloc.2
0x1794  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1799  ldarg.0
0x179a  ldnull
0x179b  stfld    class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject RSRemoteRpcServer.RpcServer::gmpNativeDelegationObject
0x17a0  ldsflda  valuetype ATL.CComQIPtr<IRsUnmanagedCallback,&_GUID_685d7a27_3348_4596_aa1c_645e9bc36012> gmpUnmanagedCallback
0x17a5  ldc.i4.0
0x17a6  conv.i8
0x17a7  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool ATL.CComPtrBase<IRsUnmanagedCallback>.!=([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtrBase<IRsUnmanagedCallback>*, [hasfieldmarshal] valuetype IRsUnmanagedCallback*)
0x17ac  brfalse.s loc_17B8
0x17ae  ldsflda  valuetype ATL.CComQIPtr<IRsUnmanagedCallback,&_GUID_685d7a27_3348_4596_aa1c_645e9bc36012> gmpUnmanagedCallback
0x17b3  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ATL.CComPtrBase<IRsUnmanagedCallback>.Release([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtrBase<IRsUnmanagedCallback>*)
0x17b8  ldarg.0
0x17b9  ldfld    class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject RSRemoteRpcServer.RpcServer::gmpUnmanagedCallbackObject
0x17be  stloc.1
0x17bf  ldloc.1
0x17c0  brfalse.s loc_17CF
0x17c2  ldloc.1
0x17c3  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x17c8  ldarg.0
0x17c9  ldnull
0x17ca  stfld    class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject RSRemoteRpcServer.RpcServer::gmpUnmanagedCallbackObject
0x17cf  ldarg.0
0x17d0  ldfld    class [ReportingServicesNativeClient]Util.SafeSafeArray RSRemoteRpcServer.RpcServer::gpWebServiceSidObject
0x17d5  stloc.0
0x17d6  ldloc.0
0x17d7  brfalse.s loc_17E6
0x17d9  ldloc.0
0x17da  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x17df  ldarg.0
0x17e0  ldnull
0x17e1  stfld    class [ReportingServicesNativeClient]Util.SafeSafeArray RSRemoteRpcServer.RpcServer::gpWebServiceSidObject
0x17e6  ret
```
