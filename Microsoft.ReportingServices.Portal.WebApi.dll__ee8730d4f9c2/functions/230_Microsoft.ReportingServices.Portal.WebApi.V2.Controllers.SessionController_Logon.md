# Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::Logon

- ea: `0x230`
- end: `0x23c`
- name: `Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::Logon`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x231`: `Logon can only be called in a server configured for Custom Authentication`

## pseudocode

```c

```

## disassembly

```asm
0x230  ldarg.0
0x231  ldstr    aLogonCanOnlyBe// "Logon can only be called in a server co"...
0x236  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult [System.Web.Http]System.Web.Http.ApiController::BadRequest(string)
0x23b  ret
```
