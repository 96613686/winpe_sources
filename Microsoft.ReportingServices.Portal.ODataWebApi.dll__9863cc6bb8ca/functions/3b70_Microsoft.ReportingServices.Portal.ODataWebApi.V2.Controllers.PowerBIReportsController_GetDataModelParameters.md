# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::GetDataModelParameters

- ea: `0x3b70`
- end: `0x3baa`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::GetDataModelParameters`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x3b70`
- `0x3be0`

## string_xrefs

- `0x3b82`: `Only reports created with version October/2020 or later and with enhanced metadata enabled can have parameters updated.`

## pseudocode

```c

```

## disassembly

```asm
0x3b70  ldarg.0
0x3b71  ldarg.1
0x3b72  ldnull
0x3b73  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::GetEntity(!!T0, string)
0x3b78  stloc.0
0x3b79  ldarg.0
0x3b7a  ldloc.0
0x3b7b  call     instance bool Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::IsModelV1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport report)
0x3b80  brfalse.s loc_3B9D
0x3b82  ldstr    aOnlyReportsCre// "Only reports created with version Octob"...
0x3b87  stloc.1
0x3b88  ldarg.0
0x3b89  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0x3b8e  ldc.i4.1
0x3b8f  ldloc.1
0x3b90  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3b95  ldarg.0
0x3b96  ldloc.1
0x3b97  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::BadRequest(string)
0x3b9c  ret
0x3b9d  ldarg.0
0x3b9e  ldloc.0
0x3b9f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataModelParameters()
0x3ba4  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::CreateOk(object)
0x3ba9  ret
```
