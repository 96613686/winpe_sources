# ::gcroot<System::String_^>..PE$AAVString@System@@

- ea: `0xaf0`
- end: `0xb08`
- name: `::gcroot<System::String_^>..PE$AAVString@System@@`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x760`
- `0xa50`

## pseudocode

```c

```

## disassembly

```asm
0xaf0  ldloca.s 0
0xaf2  ldarg.0
0xaf3  ldind.i8
0xaf4  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xaf9  ldloc.0
0xafa  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::op_Explicit(native int)
0xaff  stloc.1
0xb00  ldloca.s 1
0xb02  call     instance object [mscorlib]System.Runtime.InteropServices.GCHandle::get_Target()
0xb07  ret
```
