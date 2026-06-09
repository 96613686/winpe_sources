# ::_atexit_helper

- ea: `0xd40`
- end: `0xe5e`
- name: `::_atexit_helper`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0xf50`

## callees

- `0xce0`
- `0xd00`
- `0xd40`
- `0x1080`
- `0x1090`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldc.i4.0
0xd41  conv.i8
0xd42  stloc.s  6
0xd44  ldarg.0
0xd45  brtrue.s loc_D49
0xd47  ldc.i4.m1
0xd48  ret
0xd49  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool ?A0x15aeb141.__global_lock()
0xd4e  ldc.i4.1
0xd4f  bne.un   loc_E53
0xd54  ldarg.3
0xd55  ldind.i8
0xd56  call     void* DecodePointer(void* _Ptr)
0xd5b  stloc.1
0xd5c  ldarg.2
0xd5d  ldind.i8
0xd5e  call     void* DecodePointer(void* _Ptr)
0xd63  stloc.0
0xd64  ldloc.0
0xd65  ldloc.1
0xd66  sub
0xd67  stloc.s  5
0xd69  ldarg.1
0xd6a  ldind.i8
0xd6b  ldc.i4.1
0xd6c  conv.i8
0xd6d  sub
0xd6e  ldloc.s  5
0xd70  ldc.i4.3
0xd71  shr.un
0xd72  bge.un   loc_E24
0xd77  ldarg.1
0xd78  ldind.i8
0xd79  ldc.i4.8
0xd7a  conv.i8
0xd7b  mul
0xd7c  stloc.3
0xd7d  ldloc.3
0xd7e  ldc.i4   0x1000
0xd83  conv.i8
0xd84  blt.un.s loc_D8E
0xd86  ldc.i4   0x1000
0xd8b  conv.i8
0xd8c  br.s     loc_D8F
0xd8e  ldloc.3
0xd8f  stloc.s  0xC
0xd91  ldloca.s 0xB
0xd93  ldloc.3
0xd94  ldloc.s  0xC
0xd96  add
0xd97  conv.i4
0xd98  call     instance void [mscorlib]System.IntPtr::.ctor(int32)
0xd9d  ldloca.s 0xA
0xd9f  ldloc.1
0xda0  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xda5  ldloc.s  0xA
0xda7  ldloc.s  0xB
0xda9  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::ReAllocHGlobal(native int, native int)
0xdae  stloc.s  0xE
0xdb0  ldloca.s 0xE
0xdb2  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0xdb7  ldloc.s  5
0xdb9  add
0xdba  stloc.0
0xdbb  ldloca.s 0xE
0xdbd  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0xdc2  stloc.1
0xdc3  ldarg.1
0xdc4  ldind.i8
0xdc5  stloc.2
0xdc6  ldc.i4   0x200
0xdcb  conv.i8
0xdcc  ldloc.2
0xdcd  blt.un.s loc_DD2
0xdcf  ldloc.2
0xdd0  br.s     loc_DD8
0xdd2  ldc.i4   0x200
0xdd7  conv.i8
0xdd8  stloc.s  9
0xdda  ldarg.1
0xddb  ldloc.2
0xddc  ldloc.s  9
0xdde  add
0xddf  stind.i8
0xde0  leave.s  loc_E24
0xde2  pop
0xde3  ldloca.s 8
0xde5  ldarg.1
0xde6  ldind.i8
0xde7  ldc.i4.8
0xde8  conv.i8
0xde9  mul
0xdea  ldc.i4.s 0xC
0xdec  conv.i8
0xded  add
0xdee  conv.i4
0xdef  call     instance void [mscorlib]System.IntPtr::.ctor(int32)
0xdf4  ldloca.s 7
0xdf6  ldloc.1
0xdf7  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xdfc  ldloc.s  7
0xdfe  ldloc.s  8
0xe00  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::ReAllocHGlobal(native int, native int)
0xe05  stloc.s  0xD
0xe07  ldloca.s 0xD
0xe09  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0xe0e  ldloc.1
0xe0f  sub
0xe10  ldloc.0
0xe11  add
0xe12  stloc.0
0xe13  ldloca.s 0xD
0xe15  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0xe1a  stloc.1
0xe1b  ldarg.1
0xe1c  dup
0xe1d  ldind.i8
0xe1e  ldc.i4.4
0xe1f  conv.i8
0xe20  add
0xe21  stind.i8
0xe22  leave.s  loc_E24
0xe24  ldloc.0
0xe25  ldarg.0
0xe26  stind.i8
0xe27  ldloc.0
0xe28  ldc.i4.8
0xe29  conv.i8
0xe2a  add
0xe2b  stloc.0
0xe2c  ldarg.0
0xe2d  stloc.s  6
0xe2f  ldarg.3
0xe30  ldloc.1
0xe31  call     void* EncodePointer(void* _Ptr)
0xe36  stind.i8
0xe37  ldarg.2
0xe38  ldloc.0
0xe39  call     void* EncodePointer(void* _Ptr)
0xe3e  stind.i8
0xe3f  leave.s  loc_E46
0xe41  pop
0xe42  leave.s  loc_E44
0xe44  leave.s  loc_E4F
0xe46  leave.s  loc_E4F
0xe48  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool ?A0x15aeb141.__global_unlock()
0xe4d  pop
0xe4e  endfinally
0xe4f  ldloc.s  6
0xe51  brtrue.s loc_E58
0xe53  ldc.i4.m1
0xe54  stloc.s  4
0xe56  br.s     loc_E5B
0xe58  ldc.i4.0
0xe59  stloc.s  4
0xe5b  ldloc.s  4
0xe5d  ret
```
