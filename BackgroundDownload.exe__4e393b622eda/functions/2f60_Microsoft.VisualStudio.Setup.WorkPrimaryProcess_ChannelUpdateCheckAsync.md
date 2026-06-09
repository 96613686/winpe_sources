# Microsoft.VisualStudio.Setup.WorkPrimaryProcess::ChannelUpdateCheckAsync

- ea: `0x2f60`
- end: `0x2fb9`
- name: `Microsoft.VisualStudio.Setup.WorkPrimaryProcess::ChannelUpdateCheckAsync`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5f80`

## pseudocode

```c

```

## disassembly

```asm
0x2f60  ldloca.s 0
0x2f62  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x2f67  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x2f6c  ldloca.s 0
0x2f6e  ldarg.1
0x2f6f  stfld    string <ChannelUpdateCheckAsync>d__1::instanceId
0x2f74  ldloca.s 0
0x2f76  ldarg.2
0x2f77  stfld    class [System]System.Uri <ChannelUpdateCheckAsync>d__1::installChannelUri
0x2f7c  ldloca.s 0
0x2f7e  ldarg.3
0x2f7f  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <ChannelUpdateCheckAsync>d__1::instances
0x2f84  ldloca.s 0
0x2f86  ldarg.s  4
0x2f88  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x2f8d  ldloca.s 0
0x2f8f  ldarg.s  5
0x2f91  stfld    valuetype [mscorlib]System.Threading.CancellationToken <ChannelUpdateCheckAsync>d__1::cancellationToken
0x2f96  ldloca.s 0
0x2f98  ldc.i4.m1
0x2f99  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x2f9e  ldloca.s 0
0x2fa0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x2fa5  ldloca.s 0
0x2fa7  call     T0x2B00003E
0x2fac  ldloca.s 0
0x2fae  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x2fb3  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x2fb8  ret
```
