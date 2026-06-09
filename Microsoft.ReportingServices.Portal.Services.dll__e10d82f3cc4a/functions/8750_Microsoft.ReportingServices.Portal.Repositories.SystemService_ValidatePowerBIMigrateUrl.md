# Microsoft.ReportingServices.Portal.Repositories.SystemService::ValidatePowerBIMigrateUrl

- ea: `0x8750`
- end: `0x87ce`
- name: `Microsoft.ReportingServices.Portal.Repositories.SystemService::ValidatePowerBIMigrateUrl`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x8750`
- `0xa980`
- `0x1ff60`

## string_xrefs

- `0x8792`: `http.+((.powerbi.com)|(.microsoft.com)|(.windows.net)|(.powerbigov.us)|(.powerbi.cn)|(.powerbi.de))`

## pseudocode

```c

```

## disassembly

```asm
0x8750  newobj   instance void <>c__DisplayClass37_0::.ctor()
0x8755  stloc.0
0x8756  ldloc.0
0x8757  ldarg.2
0x8758  stfld    string <>c__DisplayClass37_0::powerBIMigrateUrlPropertyName
0x875d  ldarg.1
0x875e  ldloc.0
0x875f  ldftn    instance bool <>c__DisplayClass37_0::<ValidatePowerBIMigrateUrl>b__0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0x8765  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0x876a  call     T0x2B00007B
0x876f  brfalse.s loc_87C8
0x8771  ldarg.1
0x8772  ldloc.0
0x8773  ldftn    instance bool <>c__DisplayClass37_0::<ValidatePowerBIMigrateUrl>b__1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0x8779  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0x877e  call     T0x2B000030
0x8783  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x8788  ldc.i4.1
0x8789  ldloca.s 1
0x878b  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x8790  brfalse.s loc_87B6
0x8792  ldstr    aHttpPowerbiCom// "http.+((.powerbi.com)|(.microsoft.com)|"...
0x8797  ldc.i4.s 9
0x8799  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x879e  ldloc.1
0x879f  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x87a4  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x87a9  brtrue.s loc_87C1
0x87ab  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_InvalidPowerBIMigrateUrl()
0x87b0  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIMigrateInvalidUrlException::.ctor(string)
0x87b5  throw
0x87b6  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_InvalidPowerBIMigrateUrl()
0x87bb  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIMigrateInvalidUrlException::.ctor(string)
0x87c0  throw
0x87c1  ldloc.1
0x87c2  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x87c7  ret
0x87c8  ldstr    asc_25656// ""
0x87cd  ret
```
