# RSRemoteRpcClient.RemoteLogon::DeleteEncryptedContent

- ea: `0x1a50`
- end: `0x1a8b`
- name: `RSRemoteRpcClient.RemoteLogon::DeleteEncryptedContent`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0xed0`
- `0xf30`
- `0x1600`
- `0x1630`
- `0x1a50`
- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x1a50  ldnull
0x1a51  stloc.0
0x1a52  ldc.i4.0
0x1a53  conv.i8
0x1a54  stloc.1
0x1a55  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x1a5a  ldarg.0
0x1a5b  call     class Util.SafeStringToHGlobalUni Util.SafeStringToHGlobalUni::Create(string s)
0x1a60  stloc.0
0x1a61  ldloc.0
0x1a62  call     instance unsigned int16* Util.SafeStringToHGlobalUni::ToPointer()
0x1a67  ldloca.s 1
0x1a69  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 NativeRpcDeleteEncryptedContent([hasfieldmarshal] unsigned int16*, [hasfieldmarshal] valuetype tagSAFEARRAY**)
0x1a6e  ldloc.1
0x1a6f  call     void RSRemoteRpcClient.RemoteLogon::ThrowFriendlyRpcError(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 mainError, valuetype tagSAFEARRAY* pExtendedError)
0x1a74  leave.s  loc_1A8A
0x1a76  ldloc.0
0x1a77  brfalse.s loc_1A7F
0x1a79  ldloc.0
0x1a7a  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1a7f  ldloc.1
0x1a80  brfalse.s loc_1A89
0x1a82  ldloc.1
0x1a83  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 SafeArrayDestroy([hasfieldmarshal] valuetype tagSAFEARRAY*)
0x1a88  pop
0x1a89  endfinally
0x1a8a  ret
```
