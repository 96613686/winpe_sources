# Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::GetDBConfigInfo

- ea: `0x960`
- end: `0x983`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::GetDBConfigInfo`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x960`
- `0x990`

## pseudocode

```c

```

## disassembly

```asm
0x960  ldarg.0
0x961  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::GetConfigInfoValues()
0x966  stloc.0
0x967  leave.s  loc_981
0x969  callvirt instance string [mscorlib]System.Exception::get_Message()
0x96e  call     T0x2B000002
0x973  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x978  ldarg.0
0x979  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult [System.Web.Http]System.Web.Http.ApiController::BadRequest()
0x97e  stloc.0
0x97f  leave.s  loc_981
0x981  ldloc.0
0x982  ret
```
