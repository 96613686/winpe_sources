# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::Enable

- ea: `0x8c90`
- end: `0x8cc4`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::Enable`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ef0`

## callees

- `0x8c90`

## pseudocode

```c

```

## disassembly

```asm
0x8c90  ldarg.0
0x8c91  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x8c96  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x8c9b  brtrue.s loc_8CAA
0x8c9d  ldarg.0
0x8c9e  ldarg.0
0x8c9f  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription>::GetModelStateValidationErrors()
0x8ca4  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription>::BadRequest(string)
0x8ca9  ret
0x8caa  ldarg.0
0x8cab  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_subscriptionService
0x8cb0  ldarg.0
0x8cb1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8cb6  ldarg.1
0x8cb7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::EnableSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x8cbc  ldarg.0
0x8cbd  ldc.i4.1
0x8cbe  callvirt T0x2B00003A
0x8cc3  ret
```
