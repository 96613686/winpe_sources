# Microsoft.BIServer.BIService.BIService::OnStart_0

- ea: `0xb50`
- end: `0xb7d`
- name: `Microsoft.BIServer.BIService.BIService::OnStart_0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xb50  ldloca.s 0
0xb52  ldarg.0
0xb53  stfld    class Microsoft.BIServer.BIService.BIService <OnStart>d__26::<>4__this
0xb58  ldloca.s 0
0xb5a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::Create()
0xb5f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <OnStart>d__26::<>t__builder
0xb64  ldloca.s 0
0xb66  ldc.i4.m1
0xb67  stfld    int32 <OnStart>d__26::<>1__state
0xb6c  ldloc.0
0xb6d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <OnStart>d__26::<>t__builder
0xb72  stloc.1
0xb73  ldloca.s 1
0xb75  ldloca.s 0
0xb77  call     T0x2B000006
0xb7c  ret
```
