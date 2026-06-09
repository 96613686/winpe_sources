# ::_exit_callback

- ea: `0xe60`
- end: `0xf02`
- name: `::_exit_callback`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x960`

## callees

- `0xd30`
- `0xe60`
- `0x1080`
- `0x1090`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldsfld   unsigned int64 ?A0x15aeb141.__exit_list_size
0xe65  brfalse  loc_F01
0xe6a  ldsfld   void(())* ?A0x15aeb141.__onexitbegin_m
0xe6f  call     void* DecodePointer(void* _Ptr)
0xe74  stloc.1
0xe75  ldsfld   void(())* ?A0x15aeb141.__onexitend_m
0xe7a  call     void* DecodePointer(void* _Ptr)
0xe7f  stloc.0
0xe80  ldloc.1
0xe81  ldc.i8   0xFFFFFFFFFFFFFFFF
0xe8a  beq.s    loc_EFC
0xe8c  ldloc.1
0xe8d  brfalse.s loc_EFC
0xe8f  ldloc.0
0xe90  brfalse.s loc_EFC
0xe92  ldloc.1
0xe93  stloc.s  5
0xe95  ldloc.0
0xe96  stloc.s  4
0xe98  ldloc.0
0xe99  ldc.i4.8
0xe9a  conv.i8
0xe9b  sub
0xe9c  stloc.0
0xe9d  ldloc.0
0xe9e  ldloc.1
0xe9f  blt.un.s loc_EED
0xea1  ldloc.0
0xea2  ldind.i8
0xea3  ldc.i4.0
0xea4  conv.i8
0xea5  call     void* EncodePointer(void* _Ptr)
0xeaa  beq.s    loc_E98
0xeac  ldloc.0
0xead  ldind.i8
0xeae  call     void* DecodePointer(void* _Ptr)
0xeb3  ldloc.0
0xeb4  ldc.i4.0
0xeb5  conv.i8
0xeb6  call     void* EncodePointer(void* _Ptr)
0xebb  stind.i8
0xebc  calli    T0x11000044
0xec1  ldsfld   void(())* ?A0x15aeb141.__onexitbegin_m
0xec6  call     void* DecodePointer(void* _Ptr)
0xecb  stloc.3
0xecc  ldsfld   void(())* ?A0x15aeb141.__onexitend_m
0xed1  call     void* DecodePointer(void* _Ptr)
0xed6  stloc.2
0xed7  ldloc.s  5
0xed9  ldloc.3
0xeda  bne.un.s loc_EE1
0xedc  ldloc.s  4
0xede  ldloc.2
0xedf  beq.s    loc_E98
0xee1  ldloc.3
0xee2  stloc.s  5
0xee4  ldloc.3
0xee5  stloc.1
0xee6  ldloc.2
0xee7  stloc.s  4
0xee9  ldloc.2
0xeea  stloc.0
0xeeb  br.s     loc_E98
0xeed  ldloca.s 6
0xeef  ldloc.1
0xef0  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xef5  ldloc.s  6
0xef7  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0xefc  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void ?A0x15aeb141.__dealloc_global_lock()
0xf01  ret
```
