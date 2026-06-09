# ::_initatexit_m

- ea: `0xf10`
- end: `0xf4a`
- name: `::_initatexit_m`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x7f0`

## callees

- `0xd20`
- `0xf10`
- `0x1090`

## pseudocode

```c

```

## disassembly

```asm
0xf10  ldc.i4.0
0xf11  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool ?A0x15aeb141.__alloc_global_lock()
0xf16  ldc.i4.1
0xf17  bne.un.s loc_F49
0xf19  pop
0xf1a  ldc.i4   0x100
0xf1f  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0xf24  stloc.0
0xf25  ldloca.s 0
0xf27  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0xf2c  call     void* EncodePointer(void* _Ptr)
0xf31  stsfld   void(())* ?A0x15aeb141.__onexitbegin_m
0xf36  ldsfld   void(())* ?A0x15aeb141.__onexitbegin_m
0xf3b  stsfld   void(())* ?A0x15aeb141.__onexitend_m
0xf40  ldc.i4.s 0x20
0xf42  conv.i8
0xf43  stsfld   unsigned int64 ?A0x15aeb141.__exit_list_size
0xf48  ldc.i4.1
0xf49  ret
```
