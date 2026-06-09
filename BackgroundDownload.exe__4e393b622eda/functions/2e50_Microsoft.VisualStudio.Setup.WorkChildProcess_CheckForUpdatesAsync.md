# Microsoft.VisualStudio.Setup.WorkChildProcess::CheckForUpdatesAsync

- ea: `0x2e50`
- end: `0x2e90`
- name: `Microsoft.VisualStudio.Setup.WorkChildProcess::CheckForUpdatesAsync`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2e50  ldloca.s 0
0x2e52  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::Create()
0x2e57  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x2e5c  ldloca.s 0
0x2e5e  ldarg.1
0x2e5f  stfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x2e64  ldloca.s 0
0x2e66  ldarg.s  4
0x2e68  stfld    valuetype [mscorlib]System.Threading.CancellationToken <CheckForUpdatesAsync>d__0::cancellationToken
0x2e6d  ldloca.s 0
0x2e6f  ldc.i4.m1
0x2e70  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x2e75  ldloca.s 0
0x2e77  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x2e7c  ldloca.s 0
0x2e7e  call     T0x2B00003C
0x2e83  ldloca.s 0
0x2e85  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x2e8a  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::get_Task()
0x2e8f  ret
```
