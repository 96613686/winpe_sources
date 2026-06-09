# Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::GetConfigInfoValues

- ea: `0x990`
- end: `0xa00`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::GetConfigInfoValues`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x960`

## callees

- `0x940`
- `0x990`

## pseudocode

```c

```

## disassembly

```asm
0x990  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::_cachedConfigValues
0x995  brfalse.s loc_9C7
0x997  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x99c  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::_cacheFetchDateTime
0x9a1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x9a6  ldc.r8   60.0
0x9af  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x9b4  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x9b9  brfalse.s loc_9C7
0x9bb  ldarg.0
0x9bc  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::_cachedConfigValues
0x9c1  callvirt T0x2B000009
0x9c6  ret
0x9c7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x9cc  stsfld   valuetype [mscorlib]System.DateTime Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::_cacheFetchDateTime
0x9d1  ldarg.0
0x9d2  call     instance class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.IConfigurationInfoDataAccessor Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::get_DataAccessor()
0x9d7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.IConfigurationInfoDataAccessor::GetConfigInfoValuesAsync()
0x9dc  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::get_Result()
0x9e1  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::_cachedConfigValues
0x9e6  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::_cachedConfigValues
0x9eb  brtrue.s loc_9F4
0x9ed  ldarg.0
0x9ee  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult [System.Web.Http]System.Web.Http.ApiController::BadRequest()
0x9f3  ret
0x9f4  ldarg.0
0x9f5  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::_cachedConfigValues
0x9fa  callvirt T0x2B000009
0x9ff  ret
```
