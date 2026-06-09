# RSRemoteRpcClient.RemoteLogon::DeleteKey

- ea: `0x1a90`
- end: `0x1ae3`
- name: `RSRemoteRpcClient.RemoteLogon::DeleteKey`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0xed0`
- `0xf40`
- `0x1600`
- `0x1630`
- `0x1a90`
- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x1a90  ldnull
0x1a91  stloc.1
0x1a92  ldnull
0x1a93  stloc.0
0x1a94  ldc.i4.0
0x1a95  conv.i8
0x1a96  stloc.2
0x1a97  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x1a9c  ldarg.1
0x1a9d  call     class Util.SafeStringToHGlobalUni Util.SafeStringToHGlobalUni::Create(string s)
0x1aa2  stloc.1
0x1aa3  ldarg.0
0x1aa4  call     class Util.SafeStringToHGlobalUni Util.SafeStringToHGlobalUni::Create(string s)
0x1aa9  stloc.0
0x1aaa  ldloc.0
0x1aab  call     instance unsigned int16* Util.SafeStringToHGlobalUni::ToPointer()
0x1ab0  ldloc.1
0x1ab1  call     instance unsigned int16* Util.SafeStringToHGlobalUni::ToPointer()
0x1ab6  ldloca.s 2
0x1ab8  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 NativeRpcDeleteKey([hasfieldmarshal] unsigned int16*, [hasfieldmarshal] unsigned int16*, [hasfieldmarshal] valuetype tagSAFEARRAY**)
0x1abd  ldloc.2
0x1abe  call     void RSRemoteRpcClient.RemoteLogon::ThrowFriendlyRpcError(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 mainError, valuetype tagSAFEARRAY* pExtendedError)
0x1ac3  leave.s  loc_1AE2
0x1ac5  ldloc.0
0x1ac6  brfalse.s loc_1ACE
0x1ac8  ldloc.0
0x1ac9  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1ace  ldloc.1
0x1acf  brfalse.s loc_1AD7
0x1ad1  ldloc.1
0x1ad2  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1ad7  ldloc.2
0x1ad8  brfalse.s loc_1AE1
0x1ada  ldloc.2
0x1adb  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 SafeArrayDestroy([hasfieldmarshal] valuetype tagSAFEARRAY*)
0x1ae0  pop
0x1ae1  endfinally
0x1ae2  ret
```
