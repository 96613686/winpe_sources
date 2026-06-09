# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::SafeGetSystemResourceContent

- ea: `0x98d0`
- end: `0x9947`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::SafeGetSystemResourceContent`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6270`

## callees

- `0x6a0`
- `0x98d0`
- `0x99b0`

## pseudocode

```c

```

## disassembly

```asm
0x98d0  ldarg.1
0x98d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x98d6  brfalse.s loc_98F3
0x98d8  ldarg.0
0x98d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x98de  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ParameterValueNotSupplied()
0x98e3  ldstr    aType// "type"
0x98e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x98ed  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult [System.Web.Http]System.Web.Http.ApiController::BadRequest(string)
0x98f2  ret
0x98f3  ldarg.2
0x98f4  brfalse.s loc_98FE
0x98f6  ldarg.2
0x98f7  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x98fc  starg.s  2
0x98fe  ldarg.0
0x98ff  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_systemResourceService
0x9904  ldarg.0
0x9905  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x990a  ldarg.1
0x990b  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x9910  ldarg.2
0x9911  ldloca.s 0
0x9913  ldloca.s 1
0x9915  ldloca.s 2
0x9917  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService::TryGetPayload(class [mscorlib]System.Security.Principal.IPrincipal, string, string, string&, string&, unsigned int8[]&)
0x991c  brtrue.s loc_992E
0x991e  ldarg.0
0x991f  ldarg.0
0x9920  ldnull
0x9921  ldnull
0x9922  ldarg.2
0x9923  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CreateByteArrayHttpOkResponseMessage(unsigned int8[] bytes, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType, string fileName)
0x9928  callvirt instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult [System.Web.Http]System.Web.Http.ApiController::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x992d  ret
0x992e  ldloc.0
0x992f  ldloca.s 3
0x9931  call     bool [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::TryParse(string, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue&)
0x9936  pop
0x9937  ldarg.0
0x9938  ldarg.0
0x9939  ldloc.2
0x993a  ldloc.3
0x993b  ldloc.1
0x993c  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CreateByteArrayHttpOkResponseMessage(unsigned int8[] bytes, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType, string fileName)
0x9941  callvirt instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult [System.Web.Http]System.Web.Http.ApiController::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x9946  ret
```
