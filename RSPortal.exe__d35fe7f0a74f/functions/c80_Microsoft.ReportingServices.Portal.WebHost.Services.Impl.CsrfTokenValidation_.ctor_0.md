# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::.ctor_0

- ea: `0xc80`
- end: `0xce6`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::.ctor_0`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc80`

## pseudocode

```c

```

## disassembly

```asm
0xc80  ldarg.0
0xc81  ldsfld   class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> <>c::<>9__12_0
0xc86  dup
0xc87  brtrue.s loc_CA0
0xc89  pop
0xc8a  ldsfld   class <>c <>c::<>9
0xc8f  ldftn    instance valuetype [mscorlib]System.DateTimeOffset <>c::<.ctor>b__12_0()
0xc95  newobj   instance void class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(object, native int)
0xc9a  dup
0xc9b  stsfld   class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> <>c::<>9__12_0
0xca0  stfld    class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::NowFn
0xca5  ldarg.0
0xca6  ldsfld   class [mscorlib]System.Func`1<int32> <>c::<>9__12_1
0xcab  dup
0xcac  brtrue.s loc_CC5
0xcae  pop
0xcaf  ldsfld   class <>c <>c::<>9
0xcb4  ldftn    instance int32 <>c::<.ctor>b__12_1()
0xcba  newobj   instance void class [mscorlib]System.Func`1<int32>::.ctor(object, native int)
0xcbf  dup
0xcc0  stsfld   class [mscorlib]System.Func`1<int32> <>c::<>9__12_1
0xcc5  stfld    class [mscorlib]System.Func`1<int32> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::RandomNext
0xcca  ldarg.0
0xccb  call     instance void [mscorlib]System.Object::.ctor()
0xcd0  ldarg.0
0xcd1  ldarg.1
0xcd2  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_encryptionService
0xcd7  ldarg.0
0xcd8  ldarg.2
0xcd9  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xcde  ldarg.0
0xcdf  ldarg.3
0xce0  stfld    class IProcessTokenService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_processTokenService
0xce5  ret
```
