# ::__get_default_appdomain

- ea: `0x430`
- end: `0x487`
- name: `::__get_default_appdomain`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x4a0`

## callees

- `0x3e0`
- `0x430`

## pseudocode

```c

```

## disassembly

```asm
0x430  ldc.i4.0
0x431  conv.i8
0x432  stloc.0
0x433  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype __s_GUID _GUID_cb2f6722_ab3a_11d2_9c40_00c04fa30a3e
0x438  call     valuetype [mscorlib]System.Guid <CrtImplementationDetails>.FromGUID(modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype _GUID* guid)
0x43d  stloc.3
0x43e  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype __s_GUID _GUID_cb2f6723_ab3a_11d2_9c40_00c04fa30a3e
0x443  call     valuetype [mscorlib]System.Guid <CrtImplementationDetails>.FromGUID(modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype _GUID* guid)
0x448  ldloc.3
0x449  call     native int [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeInterfaceAsIntPtr(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x44e  stloc.s  4
0x450  ldloca.s 4
0x452  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x457  stloc.0
0x458  leave.s  loc_466
0x45a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForException(class [mscorlib]System.Exception)
0x45f  stloc.1
0x460  leave.s  loc_462
0x462  ldloc.1
0x463  ldc.i4.0
0x464  blt.s    loc_485
0x466  ldloc.0
0x467  ldind.i8
0x468  ldc.i4.s 0x68
0x46a  conv.i8
0x46b  add
0x46c  ldind.i8
0x46d  stloc.2
0x46e  ldloc.0
0x46f  ldarg.0
0x470  ldloc.2
0x471  calli    T0x1100001B
0x476  stloc.1
0x477  ldloc.0
0x478  dup
0x479  ldind.i8
0x47a  ldc.i4.s 0x10
0x47c  conv.i8
0x47d  add
0x47e  ldind.i8
0x47f  calli    T0x11000002
0x484  pop
0x485  ldloc.1
0x486  ret
```
