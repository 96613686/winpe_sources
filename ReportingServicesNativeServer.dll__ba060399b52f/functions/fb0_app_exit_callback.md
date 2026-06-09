# ::_app_exit_callback

- ea: `0xfb0`
- end: `0x1071`
- name: `::_app_exit_callback`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x950`

## callees

- `0xd30`
- `0xfb0`
- `0x1080`
- `0x1090`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldsfld   unsigned int64 __exit_list_size_app_domain
0xfb5  brfalse  loc_1070
0xfba  ldsfld   void(())* __onexitbegin_app_domain
0xfbf  call     void* DecodePointer(void* _Ptr)
0xfc4  stloc.1
0xfc5  ldsfld   void(())* __onexitend_app_domain
0xfca  call     void* DecodePointer(void* _Ptr)
0xfcf  stloc.0
0xfd0  ldloc.1
0xfd1  ldc.i8   0xFFFFFFFFFFFFFFFF
0xfda  beq      loc_1059
0xfdf  ldloc.1
0xfe0  brfalse  loc_1059
0xfe5  ldloc.0
0xfe6  brfalse.s loc_1059
0xfe8  ldc.i4.0
0xfe9  conv.i8
0xfea  stloc.s  6
0xfec  ldloc.1
0xfed  stloc.s  5
0xfef  ldloc.0
0xff0  stloc.s  4
0xff2  ldc.i4.0
0xff3  conv.i8
0xff4  stloc.s  9
0xff6  ldc.i4.0
0xff7  conv.i8
0xff8  stloc.s  8
0xffa  ldloc.0
0xffb  ldc.i4.8
0xffc  conv.i8
0xffd  sub
0xffe  stloc.0
0xfff  ldloc.0
0x1000  ldloc.1
0x1001  blt.un.s loc_1010
0x1003  ldloc.0
0x1004  ldind.i8
0x1005  ldc.i4.0
0x1006  conv.i8
0x1007  call     void* EncodePointer(void* _Ptr)
0x100c  bne.un.s loc_1010
0x100e  br.s     loc_FFA
0x1010  ldloc.0
0x1011  ldloc.1
0x1012  blt.un.s loc_1059
0x1014  ldloc.0
0x1015  ldind.i8
0x1016  call     void* DecodePointer(void* _Ptr)
0x101b  stloc.s  6
0x101d  ldloc.0
0x101e  ldc.i4.0
0x101f  conv.i8
0x1020  call     void* EncodePointer(void* _Ptr)
0x1025  stind.i8
0x1026  ldloc.s  6
0x1028  calli    T0x11000044
0x102d  ldsfld   void(())* __onexitbegin_app_domain
0x1032  call     void* DecodePointer(void* _Ptr)
0x1037  stloc.3
0x1038  ldsfld   void(())* __onexitend_app_domain
0x103d  call     void* DecodePointer(void* _Ptr)
0x1042  stloc.2
0x1043  ldloc.s  5
0x1045  ldloc.3
0x1046  bne.un.s loc_104D
0x1048  ldloc.s  4
0x104a  ldloc.2
0x104b  beq.s    loc_1057
0x104d  ldloc.3
0x104e  stloc.s  5
0x1050  ldloc.3
0x1051  stloc.1
0x1052  ldloc.2
0x1053  stloc.s  4
0x1055  ldloc.2
0x1056  stloc.0
0x1057  br.s     loc_FF2
0x1059  leave.s  loc_1070
0x105b  ldloca.s 7
0x105d  ldloc.1
0x105e  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x1063  ldloc.s  7
0x1065  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x106a  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ?A0x15aeb141.__dealloc_global_lock()
0x106f  endfinally
0x1070  ret
```
