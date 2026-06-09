# Microsoft.VisualStudio.Setup.CompositionRoot::ComposeAsync

- ea: `0x2130`
- end: `0x2167`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::ComposeAsync`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5380`

## pseudocode

```c

```

## disassembly

```asm
0x2130  ldloca.s 0
0x2132  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>::Create()
0x2137  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <ComposeAsync>d__0::<>t__builder
0x213c  ldloca.s 0
0x213e  ldarg.0
0x213f  stfld    class Microsoft.VisualStudio.Setup.CommandLine <ComposeAsync>d__0::commandLine
0x2144  ldloca.s 0
0x2146  ldc.i4.m1
0x2147  stfld    int32 <ComposeAsync>d__0::<>1__state
0x214c  ldloca.s 0
0x214e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <ComposeAsync>d__0::<>t__builder
0x2153  ldloca.s 0
0x2155  call     T0x2B000017
0x215a  ldloca.s 0
0x215c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <ComposeAsync>d__0::<>t__builder
0x2161  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>::get_Task()
0x2166  ret
```
