# RSRemoteRpcClient.RemoteLogon::GetRemoteImpToken

- ea: `0x18a0`
- end: `0x18c2`
- name: `RSRemoteRpcClient.RemoteLogon::GetRemoteImpToken`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18a0`
- `0x1e80`

## pseudocode

```c

```

## disassembly

```asm
0x18a0  ldnull
0x18a1  stloc.1
0x18a2  ldc.i4.0
0x18a3  stloc.2
0x18a4  ldarg.0
0x18a5  ldarg.1
0x18a6  ldarg.2
0x18a7  ldarg.3
0x18a8  ldarg.s  4
0x18aa  ldarg.s  5
0x18ac  ldloca.s 1
0x18ae  ldloca.s 2
0x18b0  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 RSRemoteRpcClient.RemoteLogon::NativeRemoteLogon([hasfieldmarshal] string rpcEndpointName, int32 credentialsType, valuetype [mscorlib]System.Guid dataSourceId, [hasfieldmarshal] string userName, [hasfieldmarshal] string domain, [hasfieldmarshal] string password, [out] class Util.SafeToken& pImpToken, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) bool* remoteLogon)
0x18b5  stloc.0
0x18b6  ldloc.0
0x18b7  ldc.i4.0
0x18b8  bge.s    loc_18C0
0x18ba  ldloc.0
0x18bb  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x18c0  ldloc.1
0x18c1  ret
```
