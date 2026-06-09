# <ParseAsync>d__22::MoveNext

- ea: `0x1c1c0`
- end: `0x1c285`
- name: `<ParseAsync>d__22::MoveNext`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x2930`
- `0x2970`
- `0xdb20`
- `0x1c1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1c1c0  ldarg.0
0x1c1c1  ldfld    int32 <ParseAsync>d__22::<>1__state
0x1c1c6  stloc.0
0x1c1c7  ldloc.0
0x1c1c8  brfalse.s loc_1C21B
0x1c1ca  ldarg.0
0x1c1cb  ldfld    class [mscorlib]System.IServiceProvider <ParseAsync>d__22::services
0x1c1d0  ldarg.0
0x1c1d1  ldfld    string <ParseAsync>d__22::path
0x1c1d6  ldarg.0
0x1c1d7  ldfld    class [mscorlib]System.IServiceProvider <ParseAsync>d__22::services
0x1c1dc  newobj   instance void Microsoft.VisualStudio.Setup.Serialization.CatalogSerializer::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x1c1e1  ldarg.0
0x1c1e2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ParseAsync>d__22::token
0x1c1e7  call     T0x2B0000D6
0x1c1ec  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Catalog>::GetAwaiter()
0x1c1f1  stloc.2
0x1c1f2  ldloca.s 2
0x1c1f4  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Catalog>::get_IsCompleted()
0x1c1f9  brtrue.s loc_1C237
0x1c1fb  ldarg.0
0x1c1fc  ldc.i4.0
0x1c1fd  dup
0x1c1fe  stloc.0
0x1c1ff  stfld    int32 <ParseAsync>d__22::<>1__state
0x1c204  ldarg.0
0x1c205  ldloc.2
0x1c206  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Catalog> <ParseAsync>d__22::<>u__1
0x1c20b  ldarg.0
0x1c20c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Catalog> <ParseAsync>d__22::<>t__builder
0x1c211  ldloca.s 2
0x1c213  ldarg.0
0x1c214  call     T0x2B0000D7
0x1c219  leave.s  loc_1C284
0x1c21b  ldarg.0
0x1c21c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Catalog> <ParseAsync>d__22::<>u__1
0x1c221  stloc.2
0x1c222  ldarg.0
0x1c223  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Catalog> <ParseAsync>d__22::<>u__1
0x1c228  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Catalog>
0x1c22e  ldarg.0
0x1c22f  ldc.i4.m1
0x1c230  dup
0x1c231  stloc.0
0x1c232  stfld    int32 <ParseAsync>d__22::<>1__state
0x1c237  ldloca.s 2
0x1c239  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Catalog>::GetResult()
0x1c23e  dup
0x1c23f  ldarg.0
0x1c240  ldfld    valuetype Microsoft.VisualStudio.Setup.PartialManifestType <ParseAsync>d__22::defaultType
0x1c245  callvirt instance void Microsoft.VisualStudio.Setup.Catalog::SetOrigin([opt] valuetype Microsoft.VisualStudio.Setup.PartialManifestType defaultType)
0x1c24a  dup
0x1c24b  ldarg.0
0x1c24c  ldfld    valuetype Microsoft.VisualStudio.Setup.PartialManifestType <ParseAsync>d__22::defaultType
0x1c251  callvirt instance void Microsoft.VisualStudio.Setup.Catalog::SetPayloadIsDynamicEndPoint(valuetype Microsoft.VisualStudio.Setup.PartialManifestType defaultType)
0x1c256  stloc.1
0x1c257  leave.s  loc_1C270
0x1c259  stloc.3
0x1c25a  ldarg.0
0x1c25b  ldc.i4.s 0xFE
0x1c25d  stfld    int32 <ParseAsync>d__22::<>1__state
0x1c262  ldarg.0
0x1c263  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Catalog> <ParseAsync>d__22::<>t__builder
0x1c268  ldloc.3
0x1c269  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Catalog>::SetException(class [mscorlib]System.Exception)
0x1c26e  leave.s  loc_1C284
0x1c270  ldarg.0
0x1c271  ldc.i4.s 0xFE
0x1c273  stfld    int32 <ParseAsync>d__22::<>1__state
0x1c278  ldarg.0
0x1c279  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Catalog> <ParseAsync>d__22::<>t__builder
0x1c27e  ldloc.1
0x1c27f  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Catalog>::SetResult(var<u1>)
0x1c284  ret
```
