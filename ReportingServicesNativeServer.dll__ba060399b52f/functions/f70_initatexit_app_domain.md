# ::_initatexit_app_domain

- ea: `0xf70`
- end: `0xfa8`
- name: `::_initatexit_app_domain`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x830`

## callees

- `0xd20`
- `0xf70`
- `0x1090`

## pseudocode

```c

```

## disassembly

```asm
0xf70  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool ?A0x15aeb141.__alloc_global_lock()
0xf75  ldc.i4.1
0xf76  bne.un.s loc_FA6
0xf78  ldc.i4   0x100
0xf7d  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0xf82  stloc.0
0xf83  ldloca.s 0
0xf85  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0xf8a  call     void* EncodePointer(void* _Ptr)
0xf8f  stsfld   void(())* __onexitbegin_app_domain
0xf94  ldsfld   void(())* __onexitbegin_app_domain
0xf99  stsfld   void(())* __onexitend_app_domain
0xf9e  ldc.i4.s 0x20
0xfa0  conv.i8
0xfa1  stsfld   unsigned int64 __exit_list_size_app_domain
0xfa6  ldc.i4.1
0xfa7  ret
```
