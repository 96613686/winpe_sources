# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::GetSingleton

- ea: `0x72d0`
- end: `0x738d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::GetSingleton`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5370`

## callees

- `0x72d0`

## pseudocode

```c

```

## disassembly

```asm
0x72d0  ldarg.0
0x72d1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x72d6  brfalse  loc_738B
0x72db  ldarg.0
0x72dc  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x72e1  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x72e6  brfalse  loc_738B
0x72eb  ldarg.0
0x72ec  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x72f1  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x72f6  call     valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToAuthenticationType(class [mscorlib]System.Security.Principal.IIdentity)
0x72fb  stloc.0
0x72fc  ldarg.0
0x72fd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::_catalogRepository
0x7302  ldarg.0
0x7303  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7308  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x730d  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x7312  ldloc.0
0x7313  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetUserIdFromName(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType)
0x7318  stloc.1
0x7319  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.User::.ctor()
0x731e  dup
0x731f  ldloc.1
0x7320  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.User::set_Id(valuetype [mscorlib]System.Guid)
0x7325  dup
0x7326  ldarg.0
0x7327  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x732c  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x7331  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x7336  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.User::set_Username(string)
0x733b  dup
0x733c  ldarg.0
0x733d  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::_userInfoService
0x7342  ldarg.0
0x7343  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7348  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x734d  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService::GetUserDisplayName(class [mscorlib]System.Security.Principal.IIdentity)
0x7352  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.User::set_DisplayName(string)
0x7357  dup
0x7358  ldarg.0
0x7359  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::_catalogRepository
0x735e  ldarg.0
0x735f  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7364  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetFavoriteItems(class [mscorlib]System.Security.Principal.IPrincipal)
0x7369  call     T0x2B000091
0x736e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.User::set_HasFavoriteItems(bool)
0x7373  dup
0x7374  ldarg.0
0x7375  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::_catalogRepository
0x737a  ldarg.0
0x737b  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7380  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetMyReportsPath(class [mscorlib]System.Security.Principal.IPrincipal)
0x7385  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.User::set_MyReportsPath(string)
0x738a  ret
0x738b  ldnull
0x738c  ret
```
