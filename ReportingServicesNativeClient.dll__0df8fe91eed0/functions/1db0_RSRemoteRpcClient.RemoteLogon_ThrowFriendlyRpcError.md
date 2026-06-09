# RSRemoteRpcClient.RemoteLogon::ThrowFriendlyRpcError

- ea: `0x1db0`
- end: `0x1dfa`
- name: `RSRemoteRpcClient.RemoteLogon::ThrowFriendlyRpcError`
- size: `74`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18d0`
- `0x1930`
- `0x19c0`
- `0x1a50`
- `0x1a90`
- `0x1af0`
- `0x1b30`
- `0x1bd0`
- `0x1c60`
- `0x1cf0`

## callees

- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldarg.1
0x1db1  brfalse.s loc_1DF3
0x1db3  ldarg.1
0x1db4  ldc.i4.s 0x18
0x1db6  conv.i8
0x1db7  add
0x1db8  ldind.i4
0x1db9  stloc.3
0x1dba  ldloc.3
0x1dbb  brfalse.s loc_1DF3
0x1dbd  ldnull
0x1dbe  stloc.1
0x1dbf  ldarg.1
0x1dc0  ldc.i4.s 0x10
0x1dc2  conv.i8
0x1dc3  add
0x1dc4  ldind.i8
0x1dc5  stloc.s  4
0x1dc7  ldloc.3
0x1dc8  ldc.i4.1
0x1dc9  sub
0x1dca  conv.i8
0x1dcb  stloc.2
0x1dcc  ldloc.2
0x1dcd  stloc.0
0x1dce  ldloc.2
0x1dcf  ldc.i4.0
0x1dd0  conv.i8
0x1dd1  blt.s    loc_1DF1
0x1dd3  ldloc.0
0x1dd4  ldc.i4.8
0x1dd5  conv.i8
0x1dd6  mul
0x1dd7  ldloc.s  4
0x1dd9  add
0x1dda  ldind.i8
0x1ddb  newobj   instance void [mscorlib]System.String::.ctor(char*)
0x1de0  ldloc.1
0x1de1  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x1de6  stloc.1
0x1de7  ldloc.0
0x1de8  ldc.i4.1
0x1de9  conv.i8
0x1dea  sub
0x1deb  stloc.0
0x1dec  ldloc.0
0x1ded  ldc.i4.0
0x1dee  conv.i8
0x1def  bge.s    loc_1DD3
0x1df1  ldloc.1
0x1df2  throw
0x1df3  ldarg.0
0x1df4  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x1df9  ret
```
