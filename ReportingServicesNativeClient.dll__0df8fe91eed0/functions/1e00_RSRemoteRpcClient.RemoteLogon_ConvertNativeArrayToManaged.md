# RSRemoteRpcClient.RemoteLogon::ConvertNativeArrayToManaged

- ea: `0x1e00`
- end: `0x1e28`
- name: `RSRemoteRpcClient.RemoteLogon::ConvertNativeArrayToManaged`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1930`
- `0x1b30`
- `0x1bd0`
- `0x1c60`

## callees

- `0x1e00`

## pseudocode

```c

```

## disassembly

```asm
0x1e00  ldarg.0
0x1e01  brtrue.s loc_1E05
0x1e03  ldnull
0x1e04  ret
0x1e05  ldarg.0
0x1e06  ldc.i4.s 0x18
0x1e08  conv.i8
0x1e09  add
0x1e0a  ldind.i4
0x1e0b  stloc.1
0x1e0c  ldloc.1
0x1e0d  newarr   [mscorlib]System.Byte
0x1e12  stloc.0
0x1e13  ldarg.0
0x1e14  ldc.i4.s 0x10
0x1e16  conv.i8
0x1e17  add
0x1e18  ldind.i8
0x1e19  call     native int [mscorlib]System.IntPtr::op_Explicit(void*)
0x1e1e  ldloc.0
0x1e1f  ldc.i4.0
0x1e20  ldloc.1
0x1e21  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x1e26  ldloc.0
0x1e27  ret
```
