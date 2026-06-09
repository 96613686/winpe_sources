# Microsoft.BIServer.Management.WebApi.Controllers.StateController::LoadConfigSwitches

- ea: `0x880`
- end: `0x8b9`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.StateController::LoadConfigSwitches`
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
0x880  ldloca.s 0
0x882  ldarg.0
0x883  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <LoadConfigSwitches>d__5::sqlAccess
0x888  ldloca.s 0
0x88a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::Create()
0x88f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <LoadConfigSwitches>d__5::<>t__builder
0x894  ldloca.s 0
0x896  ldc.i4.m1
0x897  stfld    int32 <LoadConfigSwitches>d__5::<>1__state
0x89c  ldloc.0
0x89d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <LoadConfigSwitches>d__5::<>t__builder
0x8a2  stloc.1
0x8a3  ldloca.s 1
0x8a5  ldloca.s 0
0x8a7  call     T0x2B000007
0x8ac  ldloca.s 0
0x8ae  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <LoadConfigSwitches>d__5::<>t__builder
0x8b3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::get_Task()
0x8b8  ret
```
