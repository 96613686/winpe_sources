# RSRemoteRpcServer.RpcServer::SetActivationParameters

- ea: `0x1620`
- end: `0x1753`
- name: `RSRemoteRpcServer.RpcServer::SetActivationParameters`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x13e0`

## callees

- `0xb70`
- `0x1160`
- `0x1240`
- `0x1290`
- `0x12b0`
- `0x12c0`
- `0x1310`
- `0x1340`
- `0x1620`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldnull
0x1621  stloc.1
0x1622  ldarg.1
0x1623  ldnull
0x1624  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1629  brfalse.s loc_164F
0x162b  ldarg.1
0x162c  call     class [ReportingServicesNativeClient]Util.SafeStringToHGlobalUni [ReportingServicesNativeClient]Util.SafeStringToHGlobalUni::Create(string)
0x1631  stloc.1
0x1632  ldloc.1
0x1633  call     instance unsigned int16* [ReportingServicesNativeClient]Util.SafeStringToHGlobalUni::ToPointer()
0x1638  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) unsigned int16* SysAllocString(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int16* rpcEndpointName)
0x163d  stsfld   unsigned int16* gRpcEndpointName
0x1642  ldsfld   unsigned int16* gRpcEndpointName
0x1647  brtrue.s loc_164F
0x1649  newobj   instance void [mscorlib]System.OutOfMemoryException::.ctor()
0x164e  throw
0x164f  ldarg.2
0x1650  brfalse.s loc_16A2
0x1652  ldarg.2
0x1653  stloc.s  0xC
0x1655  ldarg.2
0x1656  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 GetLengthSid(void* rpcEndpointName)
0x165b  stloc.s  6
0x165d  ldloc.s  6
0x165f  newarr   [mscorlib]System.Byte
0x1664  stloc.s  5
0x1666  ldc.i4.0
0x1667  stloc.0
0x1668  ldloc.0
0x1669  ldloc.s  6
0x166b  bge.un.s loc_167C
0x166d  ldloc.s  5
0x166f  ldloc.0
0x1670  dup
0x1671  conv.u8
0x1672  ldarg.2
0x1673  add
0x1674  ldind.u1
0x1675  stelem.i1
0x1676  ldloc.0
0x1677  ldc.i4.1
0x1678  add
0x1679  stloc.0
0x167a  br.s     loc_1668
0x167c  ldloc.s  5
0x167e  call     class [ReportingServicesNativeClient]Util.SafeSafeArray [ReportingServicesNativeClient]Util.SafeSafeArray::Create(unsigned int8[])
0x1683  stloc.s  4
0x1685  ldarg.0
0x1686  ldloc.s  4
0x1688  stfld    class [ReportingServicesNativeClient]Util.SafeSafeArray RSRemoteRpcServer.RpcServer::gpWebServiceSidObject
0x168d  ldloc.s  4
0x168f  call     instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x1694  stloc.s  0xB
0x1696  ldloca.s 0xB
0x1698  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x169d  stsfld   valuetype tagSAFEARRAY* gpWebServiceSid
0x16a2  ldarg.3
0x16a3  brfalse.s loc_16F3
0x16a5  ldarg.3
0x16a6  call     class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject::Create(object)
0x16ab  stloc.3
0x16ac  ldarg.0
0x16ad  ldloc.3
0x16ae  stfld    class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject RSRemoteRpcServer.RpcServer::gmpNativeDelegationObject
0x16b3  ldloc.3
0x16b4  call     instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x16b9  stloc.s  0xA
0x16bb  ldloca.s 9
0x16bd  ldloca.s 0xA
0x16bf  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x16c4  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) valuetype ATL.CComPtr<IUnknown>* ATL.CComPtr<IUnknown>.{ctor}(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtr<IUnknown>* rpcEndpointName, valuetype IUnknown* webServiceUserSid)
0x16c9  pop
0x16ca  ldsflda  valuetype ATL.CComQIPtr<INativeServerDelegation,&_GUID_d60fdbd8_bc6c_4ad3_8af8_4f3d6848f40e> gmpNativeDelegation
0x16cf  ldloca.s 9
0x16d1  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) valuetype IUnknown* ATL.CComPtrBase<IUnknown>..PEAUIUnknown@@(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtrBase<IUnknown>* rpcEndpointName)
0x16d6  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) valuetype INativeServerDelegation* ATL.CComQIPtr<INativeServerDelegation,&_GUID_d60fdbd8_bc6c_4ad3_8af8_4f3d6848f40e>.=(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComQIPtr<INativeServerDelegation,&_GUID_d60fdbd8_bc6c_4ad3_8af8_4f3d6848f40e>* rpcEndpointName, valuetype IUnknown* webServiceUserSid)
0x16db  pop
0x16dc  leave.s  loc_16EC
0x16de  ldftn    modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ATL.CComPtr<IUnknown>.{dtor}([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtr<IUnknown>*)
0x16e4  ldloca.s 9
0x16e6  call     void ___CxxCallUnwindDtor(void((void*)) pDtor, void* pThis)
0x16eb  endfinally
0x16ec  ldloca.s 9
0x16ee  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ATL.CComPtr<IUnknown>.{dtor}([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtr<IUnknown>*)
0x16f3  ldarg.s  4
0x16f5  brfalse.s loc_1746
0x16f7  ldarg.s  4
0x16f9  call     class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject::Create(object)
0x16fe  stloc.2
0x16ff  ldarg.0
0x1700  ldloc.2
0x1701  stfld    class [ReportingServicesNativeClient]Util.SafeGetIUnknownForObject RSRemoteRpcServer.RpcServer::gmpUnmanagedCallbackObject
0x1706  ldloc.2
0x1707  call     instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x170c  stloc.s  8
0x170e  ldloca.s 7
0x1710  ldloca.s 8
0x1712  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x1717  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) valuetype ATL.CComPtr<IUnknown>* ATL.CComPtr<IUnknown>.{ctor}(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtr<IUnknown>* rpcEndpointName, valuetype IUnknown* webServiceUserSid)
0x171c  pop
0x171d  ldsflda  valuetype ATL.CComQIPtr<IRsUnmanagedCallback,&_GUID_685d7a27_3348_4596_aa1c_645e9bc36012> gmpUnmanagedCallback
0x1722  ldloca.s 7
0x1724  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) valuetype IUnknown* ATL.CComPtrBase<IUnknown>..PEAUIUnknown@@(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtrBase<IUnknown>* rpcEndpointName)
0x1729  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) valuetype IRsUnmanagedCallback* ATL.CComQIPtr<IRsUnmanagedCallback,&_GUID_685d7a27_3348_4596_aa1c_645e9bc36012>.=([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComQIPtr<IRsUnmanagedCallback,&_GUID_685d7a27_3348_4596_aa1c_645e9bc36012>*, valuetype IUnknown* rpcEndpointName)
0x172e  pop
0x172f  leave.s  loc_173F
0x1731  ldftn    modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ATL.CComPtr<IUnknown>.{dtor}([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtr<IUnknown>*)
0x1737  ldloca.s 7
0x1739  call     void ___CxxCallUnwindDtor(void((void*)) pDtor, void* pThis)
0x173e  endfinally
0x173f  ldloca.s 7
0x1741  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ATL.CComPtr<IUnknown>.{dtor}([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype ATL.CComPtr<IUnknown>*)
0x1746  leave.s  loc_1752
0x1748  ldloc.1
0x1749  brfalse.s loc_1751
0x174b  ldloc.1
0x174c  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1751  endfinally
0x1752  ret
```
