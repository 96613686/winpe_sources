# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::ValidateExtensionSettings

- ea: `0x3400`
- end: `0x348f`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::ValidateExtensionSettings`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x3400`

## string_xrefs

- `0x3438`: `ExtensionName`
- `0x3452`: `ExtensionName`

## pseudocode

```c

```

## disassembly

```asm
0x3400  ldarg.0
0x3401  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x3406  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x340b  brtrue.s loc_341A
0x340d  ldarg.0
0x340e  ldarg.0
0x340f  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::GetModelStateValidationErrors()
0x3414  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::BadRequest(string)
0x3419  ret
0x341a  ldarg.1
0x341b  brtrue.s loc_342A
0x341d  ldarg.0
0x341e  ldarg.0
0x341f  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::GetModelStateValidationErrors()
0x3424  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::BadRequest(string)
0x3429  ret
0x342a  ldarg.1
0x342b  ldstr    aParametervalue_0// "ParameterValues"
0x3430  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x3435  brfalse.s loc_3444
0x3437  ldarg.1
0x3438  ldstr    aExtensionname// "ExtensionName"
0x343d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x3442  brtrue.s loc_3451
0x3444  ldarg.0
0x3445  ldarg.0
0x3446  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::GetModelStateValidationErrors()
0x344b  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::BadRequest(string)
0x3450  ret
0x3451  ldarg.1
0x3452  ldstr    aExtensionname// "ExtensionName"
0x3457  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x345c  castclass [mscorlib]System.String
0x3461  stloc.0
0x3462  ldarg.1
0x3463  ldstr    aParametervalue_0// "ParameterValues"
0x3468  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x346d  castclass class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>
0x3472  stloc.1
0x3473  ldarg.0
0x3474  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::_systemService
0x3479  ldarg.0
0x347a  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x347f  ldloc.0
0x3480  ldloc.1
0x3481  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ValidateExtensionSettings(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>)
0x3486  stloc.2
0x3487  ldarg.0
0x3488  ldloc.2
0x3489  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::CreateOk(object)
0x348e  ret
```
