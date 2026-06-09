# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::Disable

- ea: `0x8cd0`
- end: `0x8d04`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::Disable`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5f00`

## callees

- `0x8cd0`

## pseudocode

```c

```

## disassembly

```asm
0x8cd0  ldarg.0
0x8cd1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x8cd6  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x8cdb  brtrue.s loc_8CEA
0x8cdd  ldarg.0
0x8cde  ldarg.0
0x8cdf  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription>::GetModelStateValidationErrors()
0x8ce4  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription>::BadRequest(string)
0x8ce9  ret
0x8cea  ldarg.0
0x8ceb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_subscriptionService
0x8cf0  ldarg.0
0x8cf1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8cf6  ldarg.1
0x8cf7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::DisableSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x8cfc  ldarg.0
0x8cfd  ldc.i4.1
0x8cfe  callvirt T0x2B00003A
0x8d03  ret
```
