# System.Web.Compilation.CompilationMutex::WaitOne

- ea: `0x17d830`
- end: `0x17d8b8`
- name: `System.Web.Compilation.CompilationMutex::WaitOne`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x17d990`

## callees

- `0x30990`
- `0x34fa0`
- `0x17d830`

## string_xrefs

- `0x17d847`: `CompilationMutex_Null`
- `0x17d86a`: `CompilationMutex_Drained`
- `0x17d8a7`: `CompilationMutex_Failed`

## pseudocode

```c

```

## disassembly

```asm
0x17d830  ldarg.0
0x17d831  ldflda   valuetype [mscorlib]System.Runtime.InteropServices.HandleRef System.Web.Compilation.CompilationMutex::_mutexHandle
0x17d836  call     instance native int [mscorlib]System.Runtime.InteropServices.HandleRef::get_Handle()
0x17d83b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x17d840  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x17d845  brfalse.s loc_17D857
0x17d847  ldstr    aCompilationmut_1// "CompilationMutex_Null"
0x17d84c  call     string System.Web.SR::GetString(string name)
0x17d851  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17d856  throw
0x17d857  ldarg.0
0x17d858  ldfld    int32 System.Web.Compilation.CompilationMutex::_lockStatus
0x17d85d  stloc.0
0x17d85e  ldloc.0
0x17d85f  ldc.i4.m1
0x17d860  beq.s    loc_17D86A
0x17d862  ldarg.0
0x17d863  ldfld    bool System.Web.Compilation.CompilationMutex::_draining
0x17d868  brfalse.s loc_17D87A
0x17d86a  ldstr    aCompilationmut_2// "CompilationMutex_Drained"
0x17d86f  call     string System.Web.SR::GetString(string name)
0x17d874  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17d879  throw
0x17d87a  ldarg.0
0x17d87b  ldflda   int32 System.Web.Compilation.CompilationMutex::_lockStatus
0x17d880  ldloc.0
0x17d881  ldc.i4.1
0x17d882  add
0x17d883  ldloc.0
0x17d884  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0x17d889  ldloc.0
0x17d88a  bne.un.s loc_17D857
0x17d88c  ldarg.0
0x17d88d  ldfld    valuetype [mscorlib]System.Runtime.InteropServices.HandleRef System.Web.Compilation.CompilationMutex::_mutexHandle
0x17d892  ldc.i4.m1
0x17d893  call     int32 System.Web.UnsafeNativeMethods::InstrumentedMutexGetLock(valuetype [mscorlib]System.Runtime.InteropServices.HandleRef mutex, int32 timeout)
0x17d898  ldc.i4.m1
0x17d899  bne.un.s loc_17D8B7
0x17d89b  ldarg.0
0x17d89c  ldflda   int32 System.Web.Compilation.CompilationMutex::_lockStatus
0x17d8a1  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x17d8a6  pop
0x17d8a7  ldstr    aCompilationmut_3// "CompilationMutex_Failed"
0x17d8ac  call     string System.Web.SR::GetString(string name)
0x17d8b1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17d8b6  throw
0x17d8b7  ret
```
