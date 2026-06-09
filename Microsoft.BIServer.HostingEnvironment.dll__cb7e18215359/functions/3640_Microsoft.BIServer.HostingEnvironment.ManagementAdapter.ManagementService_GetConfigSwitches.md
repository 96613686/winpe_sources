# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetConfigSwitches

- ea: `0x3640`
- end: `0x3679`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetConfigSwitches`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3640  ldloca.s 0
0x3642  ldarg.0
0x3643  stfld    class Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService <GetConfigSwitches>d__7::<>4__this
0x3648  ldloca.s 0
0x364a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>>::Create()
0x364f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>> <GetConfigSwitches>d__7::<>t__builder
0x3654  ldloca.s 0
0x3656  ldc.i4.m1
0x3657  stfld    int32 <GetConfigSwitches>d__7::<>1__state
0x365c  ldloc.0
0x365d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>> <GetConfigSwitches>d__7::<>t__builder
0x3662  stloc.1
0x3663  ldloca.s 1
0x3665  ldloca.s 0
0x3667  call     T0x2B000027
0x366c  ldloca.s 0
0x366e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>> <GetConfigSwitches>d__7::<>t__builder
0x3673  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>>::get_Task()
0x3678  ret
```
