# ::_exit_callback

- ea: `0xb80`
- end: `0xc22`
- name: `::_exit_callback`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x770`

## callees

- `0xb70`
- `0xb80`
- `0xd80`
- `0xd90`

## pseudocode

```c

```

## disassembly

```asm
0xb80  ldsfld   unsigned int64 ?A0x15aeb141.__exit_list_size
0xb85  brfalse  loc_C21
0xb8a  ldsfld   void(())* ?A0x15aeb141.__onexitbegin_m
0xb8f  call     void* DecodePointer(void* _Ptr)
0xb94  stloc.1
0xb95  ldsfld   void(())* ?A0x15aeb141.__onexitend_m
0xb9a  call     void* DecodePointer(void* _Ptr)
0xb9f  stloc.0
0xba0  ldloc.1
0xba1  ldc.i8   0xFFFFFFFFFFFFFFFF
0xbaa  beq.s    loc_C1C
0xbac  ldloc.1
0xbad  brfalse.s loc_C1C
0xbaf  ldloc.0
0xbb0  brfalse.s loc_C1C
0xbb2  ldloc.1
0xbb3  stloc.s  5
0xbb5  ldloc.0
0xbb6  stloc.s  4
0xbb8  ldloc.0
0xbb9  ldc.i4.8
0xbba  conv.i8
0xbbb  sub
0xbbc  stloc.0
0xbbd  ldloc.0
0xbbe  ldloc.1
0xbbf  blt.un.s loc_C0D
0xbc1  ldloc.0
0xbc2  ldind.i8
0xbc3  ldc.i4.0
0xbc4  conv.i8
0xbc5  call     void* EncodePointer(void* _Ptr)
0xbca  beq.s    loc_BB8
0xbcc  ldloc.0
0xbcd  ldind.i8
0xbce  call     void* DecodePointer(void* _Ptr)
0xbd3  ldloc.0
0xbd4  ldc.i4.0
0xbd5  conv.i8
0xbd6  call     void* EncodePointer(void* _Ptr)
0xbdb  stind.i8
0xbdc  calli    T0x1100007F
0xbe1  ldsfld   void(())* ?A0x15aeb141.__onexitbegin_m
0xbe6  call     void* DecodePointer(void* _Ptr)
0xbeb  stloc.3
0xbec  ldsfld   void(())* ?A0x15aeb141.__onexitend_m
0xbf1  call     void* DecodePointer(void* _Ptr)
0xbf6  stloc.2
0xbf7  ldloc.s  5
0xbf9  ldloc.3
0xbfa  bne.un.s loc_C01
0xbfc  ldloc.s  4
0xbfe  ldloc.2
0xbff  beq.s    loc_BB8
0xc01  ldloc.3
0xc02  stloc.s  5
0xc04  ldloc.3
0xc05  stloc.1
0xc06  ldloc.2
0xc07  stloc.s  4
0xc09  ldloc.2
0xc0a  stloc.0
0xc0b  br.s     loc_BB8
0xc0d  ldloca.s 6
0xc0f  ldloc.1
0xc10  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xc15  ldloc.s  6
0xc17  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0xc1c  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ?A0x15aeb141.__dealloc_global_lock()
0xc21  ret
```
