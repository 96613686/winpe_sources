# ::gcroot<System::String_^>.=

- ea: `0x920`
- end: `0x93a`
- name: `::gcroot<System::String_^>.=`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x520`
- `0x550`
- `0x570`
- `0x600`
- `0x640`
- `0x670`
- `0x860`

## pseudocode

```c

```

## disassembly

```asm
0x920  ldloca.s 0
0x922  ldarg.0
0x923  ldind.i8
0x924  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x929  ldloc.0
0x92a  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::op_Explicit(native int)
0x92f  stloc.1
0x930  ldloca.s 1
0x932  ldarg.1
0x933  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::set_Target(object)
0x938  ldarg.0
0x939  ret
```
