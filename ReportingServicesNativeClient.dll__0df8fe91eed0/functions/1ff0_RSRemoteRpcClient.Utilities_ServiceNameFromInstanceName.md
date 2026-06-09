# RSRemoteRpcClient.Utilities::ServiceNameFromInstanceName

- ea: `0x1ff0`
- end: `0x2034`
- name: `RSRemoteRpcClient.Utilities::ServiceNameFromInstanceName`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0xef0`
- `0x1600`
- `0x1630`
- `0x1ff0`

## pseudocode

```c

```

## disassembly

```asm
0x1ff0  ldnull
0x1ff1  stloc.0
0x1ff2  ldarg.0
0x1ff3  call     class Util.SafeStringToHGlobalUni Util.SafeStringToHGlobalUni::Create(string s)
0x1ff8  stloc.0
0x1ff9  ldloc.0
0x1ffa  call     instance unsigned int16* Util.SafeStringToHGlobalUni::ToPointer()
0x1fff  ldloca.s 3
0x2001  ldc.i4   0x80
0x2006  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 NativeServiceNameFromInstanceName([hasfieldmarshal] unsigned int16*, [hasfieldmarshal] unsigned int16*, [hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32)
0x200b  stloc.1
0x200c  ldloc.0
0x200d  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x2012  ldloc.1
0x2013  ldc.i4.0
0x2014  bge.s    loc_201C
0x2016  ldloc.1
0x2017  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x201c  ldloca.s 3
0x201e  newobj   instance void [mscorlib]System.String::.ctor(char*)
0x2023  stloc.2
0x2024  leave.s  loc_2032
0x2026  ldloc.0
0x2027  brfalse.s loc_202F
0x2029  ldloc.0
0x202a  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x202f  endfinally
0x2030  ldnull
0x2031  ret
0x2032  ldloc.2
0x2033  ret
```
