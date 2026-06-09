# Microsoft.BIServer.Management.WebApi.Controllers.StateController::LoadConfigInfo

- ea: `0x8c0`
- end: `0x8f9`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.StateController::LoadConfigInfo`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0x8c0  ldloca.s 0
0x8c2  ldarg.0
0x8c3  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <LoadConfigInfo>d__6::sqlAccess
0x8c8  ldloca.s 0
0x8ca  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::Create()
0x8cf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>t__builder
0x8d4  ldloca.s 0
0x8d6  ldc.i4.m1
0x8d7  stfld    int32 <LoadConfigInfo>d__6::<>1__state
0x8dc  ldloc.0
0x8dd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>t__builder
0x8e2  stloc.1
0x8e3  ldloca.s 1
0x8e5  ldloca.s 0
0x8e7  call     T0x2B000008
0x8ec  ldloca.s 0
0x8ee  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>t__builder
0x8f3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::get_Task()
0x8f8  ret
```
