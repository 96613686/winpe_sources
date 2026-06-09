# Microsoft.VisualStudio.Setup.WorkPrimaryProcess::CheckForUpdatesAsync

- ea: `0x2f00`
- end: `0x2f58`
- name: `Microsoft.VisualStudio.Setup.WorkPrimaryProcess::CheckForUpdatesAsync`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2f00  ldloca.s 0
0x2f02  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::Create()
0x2f07  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x2f0c  ldloca.s 0
0x2f0e  ldarg.0
0x2f0f  stfld    class Microsoft.VisualStudio.Setup.WorkPrimaryProcess <CheckForUpdatesAsync>d__0::<>4__this
0x2f14  ldloca.s 0
0x2f16  ldarg.1
0x2f17  stfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x2f1c  ldloca.s 0
0x2f1e  ldarg.2
0x2f1f  stfld    string <CheckForUpdatesAsync>d__0::instanceId
0x2f24  ldloca.s 0
0x2f26  ldarg.3
0x2f27  stfld    class [System]System.Uri <CheckForUpdatesAsync>d__0::installChannelUri
0x2f2c  ldloca.s 0
0x2f2e  ldarg.s  4
0x2f30  stfld    valuetype [mscorlib]System.Threading.CancellationToken <CheckForUpdatesAsync>d__0::cancellationToken
0x2f35  ldloca.s 0
0x2f37  ldc.i4.m1
0x2f38  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x2f3d  ldloca.s 0
0x2f3f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x2f44  ldloca.s 0
0x2f46  call     T0x2B00003D
0x2f4b  ldloca.s 0
0x2f4d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x2f52  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::get_Task()
0x2f57  ret
```
