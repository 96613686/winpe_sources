# ::<CrtImplementationDetails>.DoCallBackInDefaultDomain

- ea: `0x4e0`
- end: `0x541`
- name: `::<CrtImplementationDetails>.DoCallBackInDefaultDomain`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x690`
- `0x990`

## callees

- `0x3e0`
- `0x4a0`
- `0x4e0`

## pseudocode

```c

```

## disassembly

```asm
0x4e0  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype __s_GUID _GUID_90f1a06c_7712_4762_86b5_7a5eba6bdb02
0x4e5  call     valuetype [mscorlib]System.Guid <CrtImplementationDetails>.FromGUID(modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype _GUID* guid)
0x4ea  stloc.s  4
0x4ec  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype __s_GUID _GUID_90f1a06e_7712_4762_86b5_7a5eba6bdb02
0x4f1  call     valuetype [mscorlib]System.Guid <CrtImplementationDetails>.FromGUID(modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype _GUID* guid)
0x4f6  ldloc.s  4
0x4f8  call     native int [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeInterfaceAsIntPtr(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4fd  stloc.s  5
0x4ff  ldloca.s 5
0x501  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x506  stloc.0
0x507  call     class [mscorlib]System.AppDomain <CrtImplementationDetails>.GetDefaultDomain()
0x50c  stloc.3
0x50d  ldloc.0
0x50e  ldind.i8
0x50f  ldc.i4.s 0x40
0x511  conv.i8
0x512  add
0x513  ldind.i8
0x514  stloc.2
0x515  ldloc.0
0x516  ldloc.3
0x517  call     instance int32 [mscorlib]System.AppDomain::get_Id()
0x51c  ldarg.0
0x51d  ldarg.1
0x51e  ldloc.2
0x51f  calli    T0x1100001A
0x524  stloc.1
0x525  ldloc.1
0x526  ldc.i4.0
0x527  bge.s    loc_52F
0x529  ldloc.1
0x52a  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x52f  leave.s  loc_540
0x531  ldloc.0
0x532  dup
0x533  ldind.i8
0x534  ldc.i4.s 0x10
0x536  conv.i8
0x537  add
0x538  ldind.i8
0x539  calli    T0x11000002
0x53e  pop
0x53f  endfinally
0x540  ret
```
