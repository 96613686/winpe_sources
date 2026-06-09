# <LoadConfigSwitches>d__5::MoveNext

- ea: `0xfd0`
- end: `0x10ad`
- name: `<LoadConfigSwitches>d__5::MoveNext`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x730`
- `0xfd0`

## string_xrefs

- `0xfeb`: `LoadConfigSwitches`

## pseudocode

```c

```

## disassembly

```asm
0xfd0  ldarg.0
0xfd1  ldfld    int32 <LoadConfigSwitches>d__5::<>1__state
0xfd6  stloc.0
0xfd7  ldloc.0
0xfd8  brfalse.s loc_FFB
0xfda  ldarg.0
0xfdb  ldc.i4.2
0xfdc  newarr   [mscorlib]System.String
0xfe1  dup
0xfe2  ldc.i4.0
0xfe3  ldstr    aDbstate_0// "DbState"
0xfe8  stelem.ref
0xfe9  dup
0xfea  ldc.i4.1
0xfeb  ldstr    aLoadconfigswit// "LoadConfigSwitches"
0xff0  stelem.ref
0xff1  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0xff6  stfld    class [mscorlib]System.IDisposable <LoadConfigSwitches>d__5::<>7__wrap1
0xffb  nop
0xffc  ldloc.0
0xffd  brfalse.s loc_103E
0xfff  ldarg.0
0x1000  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <LoadConfigSwitches>d__5::sqlAccess
0x1005  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ConfigurationInfoDataAccessor::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess)
0x100a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ConfigurationInfoDataAccessor::GetConfigInfoValuesAsync()
0x100f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::GetAwaiter()
0x1014  stloc.2
0x1015  ldloca.s 2
0x1017  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::get_IsCompleted()
0x101c  brtrue.s loc_105A
0x101e  ldarg.0
0x101f  ldc.i4.0
0x1020  dup
0x1021  stloc.0
0x1022  stfld    int32 <LoadConfigSwitches>d__5::<>1__state
0x1027  ldarg.0
0x1028  ldloc.2
0x1029  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigSwitches>d__5::<>u__1
0x102e  ldarg.0
0x102f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <LoadConfigSwitches>d__5::<>t__builder
0x1034  ldloca.s 2
0x1036  ldarg.0
0x1037  call     T0x2B000010
0x103c  leave.s  loc_10AC
0x103e  ldarg.0
0x103f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigSwitches>d__5::<>u__1
0x1044  stloc.2
0x1045  ldarg.0
0x1046  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigSwitches>d__5::<>u__1
0x104b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>
0x1051  ldarg.0
0x1052  ldc.i4.m1
0x1053  dup
0x1054  stloc.0
0x1055  stfld    int32 <LoadConfigSwitches>d__5::<>1__state
0x105a  ldloca.s 2
0x105c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::GetResult()
0x1061  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.BIServer.Management.WebApi.Controllers.StateController::GetConfigSwitches(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x1066  stloc.1
0x1067  leave.s  loc_1098
0x1069  ldloc.0
0x106a  ldc.i4.0
0x106b  bge.s    loc_1080
0x106d  ldarg.0
0x106e  ldfld    class [mscorlib]System.IDisposable <LoadConfigSwitches>d__5::<>7__wrap1
0x1073  brfalse.s loc_1080
0x1075  ldarg.0
0x1076  ldfld    class [mscorlib]System.IDisposable <LoadConfigSwitches>d__5::<>7__wrap1
0x107b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1080  endfinally
0x1081  stloc.3
0x1082  ldarg.0
0x1083  ldc.i4.s 0xFE
0x1085  stfld    int32 <LoadConfigSwitches>d__5::<>1__state
0x108a  ldarg.0
0x108b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <LoadConfigSwitches>d__5::<>t__builder
0x1090  ldloc.3
0x1091  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::SetException(class [mscorlib]System.Exception)
0x1096  leave.s  loc_10AC
0x1098  ldarg.0
0x1099  ldc.i4.s 0xFE
0x109b  stfld    int32 <LoadConfigSwitches>d__5::<>1__state
0x10a0  ldarg.0
0x10a1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <LoadConfigSwitches>d__5::<>t__builder
0x10a6  ldloc.1
0x10a7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::SetResult(var<u1>)
0x10ac  ret
```
