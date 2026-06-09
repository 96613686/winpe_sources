# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::CheckDataSourceConnection

- ea: `0x3d20`
- end: `0x3db9`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::CheckDataSourceConnection`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x710`
- `0x3d20`
- `0xcfc0`

## pseudocode

```c

```

## disassembly

```asm
0x3d20  ldarg.1
0x3d21  ldloca.s 0
0x3d23  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x3d28  brtrue.s loc_3D31
0x3d2a  ldarg.0
0x3d2b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::NotFound()
0x3d30  ret
0x3d31  ldarg.2
0x3d32  brfalse.s loc_3D4E
0x3d34  ldarg.0
0x3d35  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x3d3a  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x3d3f  brfalse.s loc_3D4E
0x3d41  ldarg.2
0x3d42  ldstr    aDatasourcename// "DataSourceName"
0x3d47  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x3d4c  brtrue.s loc_3D5B
0x3d4e  ldarg.0
0x3d4f  ldarg.0
0x3d50  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::GetModelStateValidationErrors()
0x3d55  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::BadRequest(string)
0x3d5a  ret
0x3d5b  ldarg.2
0x3d5c  ldstr    aDatasourcename// "DataSourceName"
0x3d61  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x3d66  callvirt instance string [mscorlib]System.Object::ToString()
0x3d6b  ldloca.s 1
0x3d6d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x3d72  brtrue.s loc_3D7B
0x3d74  ldarg.0
0x3d75  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::NotFound()
0x3d7a  ret
0x3d7b  nop
0x3d7c  ldarg.0
0x3d7d  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_powerBIReportsControllerHelper
0x3d82  ldloc.0
0x3d83  ldloc.1
0x3d84  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSourceCheckResult Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::CheckDataSourceConnection(valuetype [mscorlib]System.Guid key, valuetype [mscorlib]System.Guid dataSourceId)
0x3d89  stloc.2
0x3d8a  leave.s  loc_3DAE
0x3d8c  stloc.3
0x3d8d  ldloc.3
0x3d8e  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCountException
0x3d93  brtrue.s loc_3D9D
0x3d95  ldloc.3
0x3d96  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceTypeException
0x3d9b  brfalse.s loc_3DAC
0x3d9d  ldarg.0
0x3d9e  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_InvalidDataSourceForTestConnectionPbi()
0x3da3  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::BadRequest(string)
0x3da8  stloc.s  4
0x3daa  leave.s  loc_3DB6
0x3dac  rethrow
0x3dae  ldarg.0
0x3daf  ldloc.2
0x3db0  callvirt T0x2B000066
0x3db5  ret
0x3db6  ldloc.s  4
0x3db8  ret
```
