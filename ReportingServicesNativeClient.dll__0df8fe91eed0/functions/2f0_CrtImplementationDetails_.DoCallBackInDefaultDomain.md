# ::<CrtImplementationDetails>.DoCallBackInDefaultDomain

- ea: `0x2f0`
- end: `0x351`
- name: `::<CrtImplementationDetails>.DoCallBackInDefaultDomain`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x4a0`
- `0x7a0`

## callees

- `0x1f0`
- `0x2b0`
- `0x2f0`

## pseudocode

```c

```

## disassembly

```asm
0x2f0  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype __s_GUID _GUID_90f1a06c_7712_4762_86b5_7a5eba6bdb02
0x2f5  call     valuetype [mscorlib]System.Guid <CrtImplementationDetails>.FromGUID(modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype _GUID* guid)
0x2fa  stloc.s  4
0x2fc  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype __s_GUID _GUID_90f1a06e_7712_4762_86b5_7a5eba6bdb02
0x301  call     valuetype [mscorlib]System.Guid <CrtImplementationDetails>.FromGUID(modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype _GUID* guid)
0x306  ldloc.s  4
0x308  call     native int [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeInterfaceAsIntPtr(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x30d  stloc.s  5
0x30f  ldloca.s 5
0x311  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x316  stloc.0
0x317  call     class [mscorlib]System.AppDomain <CrtImplementationDetails>.GetDefaultDomain()
0x31c  stloc.3
0x31d  ldloc.0
0x31e  ldind.i8
0x31f  ldc.i4.s 0x40
0x321  conv.i8
0x322  add
0x323  ldind.i8
0x324  stloc.2
0x325  ldloc.0
0x326  ldloc.3
0x327  call     instance int32 [mscorlib]System.AppDomain::get_Id()
0x32c  ldarg.0
0x32d  ldarg.1
0x32e  ldloc.2
0x32f  calli    T0x11000055
0x334  stloc.1
0x335  ldloc.1
0x336  ldc.i4.0
0x337  bge.s    loc_33F
0x339  ldloc.1
0x33a  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x33f  leave.s  loc_350
0x341  ldloc.0
0x342  dup
0x343  ldind.i8
0x344  ldc.i4.s 0x10
0x346  conv.i8
0x347  add
0x348  ldind.i8
0x349  calli    T0x11000054
0x34e  pop
0x34f  endfinally
0x350  ret
```
