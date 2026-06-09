# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::.ctor

- ea: `0xbf0`
- end: `0xc76`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::.ctor`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0xbf0`
- `0x3ae0`

## string_xrefs

- `0xc43`: `encryptionService`

## pseudocode

```c

```

## disassembly

```asm
0xbf0  ldarg.0
0xbf1  ldsfld   class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> <>c::<>9__11_0
0xbf6  dup
0xbf7  brtrue.s loc_C10
0xbf9  pop
0xbfa  ldsfld   class <>c <>c::<>9
0xbff  ldftn    instance valuetype [mscorlib]System.DateTimeOffset <>c::<.ctor>b__11_0()
0xc05  newobj   instance void class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(object, native int)
0xc0a  dup
0xc0b  stsfld   class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> <>c::<>9__11_0
0xc10  stfld    class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::NowFn
0xc15  ldarg.0
0xc16  ldsfld   class [mscorlib]System.Func`1<int32> <>c::<>9__11_1
0xc1b  dup
0xc1c  brtrue.s loc_C35
0xc1e  pop
0xc1f  ldsfld   class <>c <>c::<>9
0xc24  ldftn    instance int32 <>c::<.ctor>b__11_1()
0xc2a  newobj   instance void class [mscorlib]System.Func`1<int32>::.ctor(object, native int)
0xc2f  dup
0xc30  stsfld   class [mscorlib]System.Func`1<int32> <>c::<>9__11_1
0xc35  stfld    class [mscorlib]System.Func`1<int32> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::RandomNext
0xc3a  ldarg.0
0xc3b  call     instance void [mscorlib]System.Object::.ctor()
0xc40  ldarg.1
0xc41  brtrue.s loc_C4E
0xc43  ldstr    aEncryptionserv// "encryptionService"
0xc48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc4d  throw
0xc4e  ldarg.2
0xc4f  brtrue.s loc_C5C
0xc51  ldstr    aLogger// "logger"
0xc56  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc5b  throw
0xc5c  ldarg.0
0xc5d  ldarg.1
0xc5e  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_encryptionService
0xc63  ldarg.0
0xc64  ldarg.2
0xc65  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xc6a  ldarg.0
0xc6b  newobj   instance void DefaultProcessTokenService::.ctor()
0xc70  stfld    class IProcessTokenService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_processTokenService
0xc75  ret
```
