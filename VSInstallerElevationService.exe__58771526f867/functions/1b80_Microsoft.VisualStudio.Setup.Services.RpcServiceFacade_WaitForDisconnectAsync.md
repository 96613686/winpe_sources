# Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::WaitForDisconnectAsync

- ea: `0x1b80`
- end: `0x1bb7`
- name: `Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::WaitForDisconnectAsync`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1b80  ldloca.s 0
0x1b82  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x1b87  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForDisconnectAsync>d__3::<>t__builder
0x1b8c  ldloca.s 0
0x1b8e  ldarg.0
0x1b8f  stfld    class Microsoft.VisualStudio.Setup.Services.RpcServiceFacade <WaitForDisconnectAsync>d__3::<>4__this
0x1b94  ldloca.s 0
0x1b96  ldc.i4.m1
0x1b97  stfld    int32 <WaitForDisconnectAsync>d__3::<>1__state
0x1b9c  ldloca.s 0
0x1b9e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForDisconnectAsync>d__3::<>t__builder
0x1ba3  ldloca.s 0
0x1ba5  call     T0x2B000019
0x1baa  ldloca.s 0
0x1bac  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForDisconnectAsync>d__3::<>t__builder
0x1bb1  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x1bb6  ret
```
