# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::ValidateExtensionSettings

- ea: `0x8e40`
- end: `0x8ecf`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::ValidateExtensionSettings`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x8e40`

## string_xrefs

- `0x8e78`: `ExtensionName`
- `0x8e92`: `ExtensionName`

## pseudocode

```c

```

## disassembly

```asm
0x8e40  ldarg.0
0x8e41  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x8e46  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x8e4b  brtrue.s loc_8E5A
0x8e4d  ldarg.0
0x8e4e  ldarg.0
0x8e4f  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::GetModelStateValidationErrors()
0x8e54  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::BadRequest(string)
0x8e59  ret
0x8e5a  ldarg.1
0x8e5b  brtrue.s loc_8E6A
0x8e5d  ldarg.0
0x8e5e  ldarg.0
0x8e5f  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::GetModelStateValidationErrors()
0x8e64  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::BadRequest(string)
0x8e69  ret
0x8e6a  ldarg.1
0x8e6b  ldstr    aParametervalue_0// "ParameterValues"
0x8e70  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x8e75  brfalse.s loc_8E84
0x8e77  ldarg.1
0x8e78  ldstr    aExtensionname// "ExtensionName"
0x8e7d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x8e82  brtrue.s loc_8E91
0x8e84  ldarg.0
0x8e85  ldarg.0
0x8e86  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::GetModelStateValidationErrors()
0x8e8b  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::BadRequest(string)
0x8e90  ret
0x8e91  ldarg.1
0x8e92  ldstr    aExtensionname// "ExtensionName"
0x8e97  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x8e9c  castclass [mscorlib]System.String
0x8ea1  stloc.0
0x8ea2  ldarg.1
0x8ea3  ldstr    aParametervalue_0// "ParameterValues"
0x8ea8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x8ead  castclass class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>
0x8eb2  stloc.1
0x8eb3  ldarg.0
0x8eb4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_systemService
0x8eb9  ldarg.0
0x8eba  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8ebf  ldloc.0
0x8ec0  ldloc.1
0x8ec1  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ValidateExtensionSettings(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>)
0x8ec6  stloc.2
0x8ec7  ldarg.0
0x8ec8  ldloc.2
0x8ec9  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::CreateOk(object)
0x8ece  ret
```
