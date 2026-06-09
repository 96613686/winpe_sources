# ::gcroot<System::String_^>..PE$AAVString@System@@

- ea: `0x900`
- end: `0x918`
- name: `::gcroot<System::String_^>..PE$AAVString@System@@`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x570`
- `0x860`

## pseudocode

```c

```

## disassembly

```asm
0x900  ldloca.s 0
0x902  ldarg.0
0x903  ldind.i8
0x904  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x909  ldloc.0
0x90a  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::op_Explicit(native int)
0x90f  stloc.1
0x910  ldloca.s 1
0x912  call     instance object [mscorlib]System.Runtime.InteropServices.GCHandle::get_Target()
0x917  ret
```
