# ::_app_exit_callback

- ea: `0xcb0`
- end: `0xd71`
- name: `::_app_exit_callback`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x760`

## callees

- `0xb70`
- `0xcb0`
- `0xd80`
- `0xd90`

## pseudocode

```c

```

## disassembly

```asm
0xcb0  ldsfld   unsigned int64 __exit_list_size_app_domain
0xcb5  brfalse  loc_D70
0xcba  ldsfld   void(())* __onexitbegin_app_domain
0xcbf  call     void* DecodePointer(void* _Ptr)
0xcc4  stloc.1
0xcc5  ldsfld   void(())* __onexitend_app_domain
0xcca  call     void* DecodePointer(void* _Ptr)
0xccf  stloc.0
0xcd0  ldloc.1
0xcd1  ldc.i8   0xFFFFFFFFFFFFFFFF
0xcda  beq      loc_D59
0xcdf  ldloc.1
0xce0  brfalse  loc_D59
0xce5  ldloc.0
0xce6  brfalse.s loc_D59
0xce8  ldc.i4.0
0xce9  conv.i8
0xcea  stloc.s  6
0xcec  ldloc.1
0xced  stloc.s  5
0xcef  ldloc.0
0xcf0  stloc.s  4
0xcf2  ldc.i4.0
0xcf3  conv.i8
0xcf4  stloc.s  9
0xcf6  ldc.i4.0
0xcf7  conv.i8
0xcf8  stloc.s  8
0xcfa  ldloc.0
0xcfb  ldc.i4.8
0xcfc  conv.i8
0xcfd  sub
0xcfe  stloc.0
0xcff  ldloc.0
0xd00  ldloc.1
0xd01  blt.un.s loc_D10
0xd03  ldloc.0
0xd04  ldind.i8
0xd05  ldc.i4.0
0xd06  conv.i8
0xd07  call     void* EncodePointer(void* _Ptr)
0xd0c  bne.un.s loc_D10
0xd0e  br.s     loc_CFA
0xd10  ldloc.0
0xd11  ldloc.1
0xd12  blt.un.s loc_D59
0xd14  ldloc.0
0xd15  ldind.i8
0xd16  call     void* DecodePointer(void* _Ptr)
0xd1b  stloc.s  6
0xd1d  ldloc.0
0xd1e  ldc.i4.0
0xd1f  conv.i8
0xd20  call     void* EncodePointer(void* _Ptr)
0xd25  stind.i8
0xd26  ldloc.s  6
0xd28  calli    T0x1100007F
0xd2d  ldsfld   void(())* __onexitbegin_app_domain
0xd32  call     void* DecodePointer(void* _Ptr)
0xd37  stloc.3
0xd38  ldsfld   void(())* __onexitend_app_domain
0xd3d  call     void* DecodePointer(void* _Ptr)
0xd42  stloc.2
0xd43  ldloc.s  5
0xd45  ldloc.3
0xd46  bne.un.s loc_D4D
0xd48  ldloc.s  4
0xd4a  ldloc.2
0xd4b  beq.s    loc_D57
0xd4d  ldloc.3
0xd4e  stloc.s  5
0xd50  ldloc.3
0xd51  stloc.1
0xd52  ldloc.2
0xd53  stloc.s  4
0xd55  ldloc.2
0xd56  stloc.0
0xd57  br.s     loc_CF2
0xd59  leave.s  loc_D70
0xd5b  ldloca.s 7
0xd5d  ldloc.1
0xd5e  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xd63  ldloc.s  7
0xd65  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0xd6a  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ?A0x15aeb141.__dealloc_global_lock()
0xd6f  endfinally
0xd70  ret
```
