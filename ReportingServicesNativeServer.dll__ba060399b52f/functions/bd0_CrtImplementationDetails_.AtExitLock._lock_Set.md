# ::<CrtImplementationDetails>.AtExitLock._lock_Set

- ea: `0xbd0`
- end: `0xc11`
- name: `::<CrtImplementationDetails>.AtExitLock._lock_Set`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xbc0`

## callees

- `0xb90`
- `0xbd0`

## pseudocode

```c

```

## disassembly

```asm
0xbd0  call     modopt([mscorlib]System.Runtime.CompilerServices.IsBoxed) modopt([mscorlib]System.Runtime.InteropServices.GCHandle) class [mscorlib]System.ValueType <CrtImplementationDetails>.AtExitLock._handle()
0xbd5  stloc.0
0xbd6  ldloc.0
0xbd7  brtrue.s loc_C04
0xbd9  ldarg.0
0xbda  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::Alloc(object)
0xbdf  box      [mscorlib]System.Runtime.InteropServices.GCHandle
0xbe4  stloc.0
0xbe5  ldloc.0
0xbe6  unbox    [mscorlib]System.Runtime.InteropServices.GCHandle
0xbeb  ldobj    [mscorlib]System.Runtime.InteropServices.GCHandle
0xbf0  call     native int [mscorlib]System.Runtime.InteropServices.GCHandle::ToIntPtr(valuetype [mscorlib]System.Runtime.InteropServices.GCHandle)
0xbf5  stloc.1
0xbf6  ldloca.s 1
0xbf8  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0xbfd  stsfld   void* ?_lock@AtExitLock@<CrtImplementationDetails>@@$$Q0PEAXEA
0xc02  br.s     loc_C10
0xc04  ldloc.0
0xc05  unbox    [mscorlib]System.Runtime.InteropServices.GCHandle
0xc0a  ldarg.0
0xc0b  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::set_Target(object)
0xc10  ret
```
