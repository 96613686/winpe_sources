# ::gcroot<System::String_^>.=

- ea: `0xb10`
- end: `0xb2a`
- name: `::gcroot<System::String_^>.=`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x710`
- `0x740`
- `0x760`
- `0x7f0`
- `0x830`
- `0x860`
- `0xa50`

## pseudocode

```c

```

## disassembly

```asm
0xb10  ldloca.s 0
0xb12  ldarg.0
0xb13  ldind.i8
0xb14  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xb19  ldloc.0
0xb1a  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::op_Explicit(native int)
0xb1f  stloc.1
0xb20  ldloca.s 1
0xb22  ldarg.1
0xb23  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::set_Target(object)
0xb28  ldarg.0
0xb29  ret
```
