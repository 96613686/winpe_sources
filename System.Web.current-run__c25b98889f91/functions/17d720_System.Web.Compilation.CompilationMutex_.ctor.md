# System.Web.Compilation.CompilationMutex::.ctor

- ea: `0x17d720`
- end: `0x17d7cc`
- name: `System.Web.Compilation.CompilationMutex::.ctor`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x17d930`

## callees

- `0x30970`
- `0x34fa0`
- `0x56ac0`
- `0x17d720`

## string_xrefs

- `0x17d726`: `CompilationMutexName`
- `0x17d7bb`: `CompilationMutex_Create`

## pseudocode

```c

```

## disassembly

```asm
0x17d720  ldarg.0
0x17d721  call     instance void [mscorlib]System.Object::.ctor()
0x17d726  ldstr    aCompilationmut// "CompilationMutexName"
0x17d72b  ldnull
0x17d72c  ldnull
0x17d72d  call     object System.Web.Util.Misc::GetAspNetRegValue(string subKey, string valueName, object defaultValue)
0x17d732  castclass [mscorlib]System.String
0x17d737  stloc.0
0x17d738  ldloc.0
0x17d739  brfalse.s loc_17D76F
0x17d73b  ldarg.0
0x17d73c  ldc.i4.5
0x17d73d  newarr   [mscorlib]System.String
0x17d742  dup
0x17d743  ldc.i4.0
0x17d744  ldarg.0
0x17d745  ldfld    string System.Web.Compilation.CompilationMutex::_name
0x17d74a  stelem.ref
0x17d74b  dup
0x17d74c  ldc.i4.1
0x17d74d  ldstr    aGlobal// "Global\\"
0x17d752  stelem.ref
0x17d753  dup
0x17d754  ldc.i4.2
0x17d755  ldarg.1
0x17d756  stelem.ref
0x17d757  dup
0x17d758  ldc.i4.3
0x17d759  ldstr    asc_1B81EC// "-"
0x17d75e  stelem.ref
0x17d75f  dup
0x17d760  ldc.i4.4
0x17d761  ldloc.0
0x17d762  stelem.ref
0x17d763  call     string [mscorlib]System.String::Concat(string[])
0x17d768  stfld    string System.Web.Compilation.CompilationMutex::_name
0x17d76d  br.s     loc_17D786
0x17d76f  ldarg.0
0x17d770  ldarg.0
0x17d771  ldfld    string System.Web.Compilation.CompilationMutex::_name
0x17d776  ldstr    aLocal// "Local\\"
0x17d77b  ldarg.1
0x17d77c  call     string [mscorlib]System.String::Concat(string, string, string)
0x17d781  stfld    string System.Web.Compilation.CompilationMutex::_name
0x17d786  ldarg.0
0x17d787  ldarg.2
0x17d788  stfld    string System.Web.Compilation.CompilationMutex::_comment
0x17d78d  ldarg.0
0x17d78e  ldarg.0
0x17d78f  ldarg.0
0x17d790  ldfld    string System.Web.Compilation.CompilationMutex::_name
0x17d795  call     native int System.Web.UnsafeNativeMethods::InstrumentedMutexCreate(string name)
0x17d79a  newobj   instance void [mscorlib]System.Runtime.InteropServices.HandleRef::.ctor(object, native int)
0x17d79f  stfld    valuetype [mscorlib]System.Runtime.InteropServices.HandleRef System.Web.Compilation.CompilationMutex::_mutexHandle
0x17d7a4  ldarg.0
0x17d7a5  ldflda   valuetype [mscorlib]System.Runtime.InteropServices.HandleRef System.Web.Compilation.CompilationMutex::_mutexHandle
0x17d7aa  call     instance native int [mscorlib]System.Runtime.InteropServices.HandleRef::get_Handle()
0x17d7af  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x17d7b4  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x17d7b9  brfalse.s loc_17D7CB
0x17d7bb  ldstr    aCompilationmut_0// "CompilationMutex_Create"
0x17d7c0  call     string System.Web.SR::GetString(string name)
0x17d7c5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17d7ca  throw
0x17d7cb  ret
```
