# Microsoft.BIServer.BIService.BIService::TryUpdateServiceConfigAndRestartProcesses

- ea: `0xca0`
- end: `0xcd9`
- name: `Microsoft.BIServer.BIService.BIService::TryUpdateServiceConfigAndRestartProcesses`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3030`

## pseudocode

```c

```

## disassembly

```asm
0xca0  ldloca.s 0
0xca2  ldarg.0
0xca3  stfld    class Microsoft.BIServer.BIService.BIService <TryUpdateServiceConfigAndRestartProcesses>d__32::<>4__this
0xca8  ldloca.s 0
0xcaa  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0xcaf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryUpdateServiceConfigAndRestartProcesses>d__32::<>t__builder
0xcb4  ldloca.s 0
0xcb6  ldc.i4.m1
0xcb7  stfld    int32 <TryUpdateServiceConfigAndRestartProcesses>d__32::<>1__state
0xcbc  ldloc.0
0xcbd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryUpdateServiceConfigAndRestartProcesses>d__32::<>t__builder
0xcc2  stloc.1
0xcc3  ldloca.s 1
0xcc5  ldloca.s 0
0xcc7  call     T0x2B000009
0xccc  ldloca.s 0
0xcce  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryUpdateServiceConfigAndRestartProcesses>d__32::<>t__builder
0xcd3  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0xcd8  ret
```
