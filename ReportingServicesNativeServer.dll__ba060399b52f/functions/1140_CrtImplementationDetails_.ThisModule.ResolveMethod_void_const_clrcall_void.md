# ::<CrtImplementationDetails>.ThisModule.ResolveMethod<void_const_*___clrcall(void)>

- ea: `0x1140`
- end: `0x1160`
- name: `::<CrtImplementationDetails>.ThisModule.ResolveMethod<void_const_*___clrcall(void)>`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1110`

## callees

- `0x10f0`

## pseudocode

```c

```

## disassembly

```asm
0x1140  call     valuetype [mscorlib]System.ModuleHandle <CrtImplementationDetails>.ThisModule.Handle()
0x1145  stloc.2
0x1146  ldloca.s 2
0x1148  ldarg.0
0x1149  conv.i4
0x114a  call     instance valuetype [mscorlib]System.RuntimeMethodHandle [mscorlib]System.ModuleHandle::ResolveMethodHandle(int32)
0x114f  stloc.1
0x1150  ldloca.s 1
0x1152  call     instance native int [mscorlib]System.RuntimeMethodHandle::GetFunctionPointer()
0x1157  stloc.0
0x1158  ldloca.s 0
0x115a  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x115f  ret
```
