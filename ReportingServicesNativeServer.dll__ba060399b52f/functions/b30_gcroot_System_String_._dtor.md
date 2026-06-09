# ::gcroot<System::String_^>.{dtor}

- ea: `0xb30`
- end: `0xb4c`
- name: `::gcroot<System::String_^>.{dtor}`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0xa40`

## pseudocode

```c

```

## disassembly

```asm
0xb30  ldloca.s 0
0xb32  ldarg.0
0xb33  ldind.i8
0xb34  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xb39  ldloc.0
0xb3a  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::op_Explicit(native int)
0xb3f  stloc.1
0xb40  ldloca.s 1
0xb42  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0xb47  ldarg.0
0xb48  ldc.i4.0
0xb49  conv.i8
0xb4a  stind.i8
0xb4b  ret
```
