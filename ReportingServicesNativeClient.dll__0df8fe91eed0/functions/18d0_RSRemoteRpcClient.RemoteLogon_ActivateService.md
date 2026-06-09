# RSRemoteRpcClient.RemoteLogon::ActivateService

- ea: `0x18d0`
- end: `0x1923`
- name: `RSRemoteRpcClient.RemoteLogon::ActivateService`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0xed0`
- `0xfc0`
- `0x1600`
- `0x1630`
- `0x18d0`
- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x18d0  ldnull
0x18d1  stloc.1
0x18d2  ldnull
0x18d3  stloc.0
0x18d4  ldc.i4.0
0x18d5  conv.i8
0x18d6  stloc.2
0x18d7  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x18dc  ldarg.0
0x18dd  call     class Util.SafeStringToHGlobalUni Util.SafeStringToHGlobalUni::Create(string s)
0x18e2  stloc.1
0x18e3  ldarg.1
0x18e4  call     class Util.SafeStringToHGlobalUni Util.SafeStringToHGlobalUni::Create(string s)
0x18e9  stloc.0
0x18ea  ldloc.1
0x18eb  call     instance unsigned int16* Util.SafeStringToHGlobalUni::ToPointer()
0x18f0  ldloc.0
0x18f1  call     instance unsigned int16* Util.SafeStringToHGlobalUni::ToPointer()
0x18f6  ldloca.s 2
0x18f8  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 NativeRpcActivateWebService([hasfieldmarshal] unsigned int16*, [hasfieldmarshal] unsigned int16*, valuetype tagSAFEARRAY** nativeString)
0x18fd  ldloc.2
0x18fe  call     void RSRemoteRpcClient.RemoteLogon::ThrowFriendlyRpcError(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 mainError, valuetype tagSAFEARRAY* pExtendedError)
0x1903  leave.s  loc_1922
0x1905  ldloc.1
0x1906  brfalse.s loc_190E
0x1908  ldloc.1
0x1909  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x190e  ldloc.0
0x190f  brfalse.s loc_1917
0x1911  ldloc.0
0x1912  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1917  ldloc.2
0x1918  brfalse.s loc_1921
0x191a  ldloc.2
0x191b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 SafeArrayDestroy([hasfieldmarshal] valuetype tagSAFEARRAY*)
0x1920  pop
0x1921  endfinally
0x1922  ret
```
