# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::ServiceState

- ea: `0x6130`
- end: `0x626d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::ServiceState`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x6130`
- `0x9a10`
- `0x9a70`

## pseudocode

```c

```

## disassembly

```asm
0x6130  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::.ctor()
0x6135  stloc.1
0x6136  ldloc.1
0x6137  ldc.i4.1
0x6138  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_IsAvailable(bool)
0x613d  ldloc.1
0x613e  ldarg.0
0x613f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_systemService
0x6144  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetRestrictedFeatures()
0x6149  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_RestrictedFeatures(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x614e  ldloc.1
0x614f  ldarg.0
0x6150  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_systemService
0x6155  ldarg.0
0x6156  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x615b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetAllowedSystemActions(class [mscorlib]System.Security.Principal.IPrincipal)
0x6160  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_AllowedSystemActions(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x6165  ldloc.1
0x6166  call     string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetTimeZoneFullName()
0x616b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_TimeZone(string)
0x6170  ldloc.1
0x6171  ldarg.0
0x6172  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_catalogRepository
0x6177  ldarg.0
0x6178  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x617d  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetFavoriteItems(class [mscorlib]System.Security.Principal.IPrincipal)
0x6182  call     T0x2B000091
0x6187  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_UserHasFavorites(bool)
0x618c  ldloc.1
0x618d  ldarg.0
0x618e  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetAcceptLanguage()
0x6193  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_AcceptLanguage(string)
0x6198  ldloc.1
0x6199  ldarg.0
0x619a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_systemService
0x619f  ldarg.0
0x61a0  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x61a5  ldc.i4.1
0x61a6  newarr   [mscorlib]System.String
0x61ab  dup
0x61ac  ldc.i4.0
0x61ad  ldstr    aRequireintune// "RequireIntune"
0x61b2  stelem.ref
0x61b3  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetSystemProperties(class [mscorlib]System.Security.Principal.IPrincipal, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x61b8  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Property
0x61bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x61c2  ldstr    aProp// "prop"
0x61c7  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x61cc  stloc.2
0x61cd  ldloc.2
0x61ce  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Name()
0x61d3  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x61d8  castclass [mscorlib]System.Reflection.MethodInfo
0x61dd  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x61e2  ldstr    aRequireintune// "RequireIntune"
0x61e7  ldtoken  [mscorlib]System.String
0x61ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x61f1  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x61f6  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::Equal(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0x61fb  ldnull
0x61fc  ldtoken  bool [mscorlib]System.Boolean::Parse(string)
0x6201  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6206  castclass [mscorlib]System.Reflection.MethodInfo
0x620b  ldc.i4.1
0x620c  newarr   [System.Core]System.Linq.Expressions.Expression
0x6211  dup
0x6212  ldc.i4.0
0x6213  ldloc.2
0x6214  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x6219  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x621e  castclass [mscorlib]System.Reflection.MethodInfo
0x6223  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6228  stelem.ref
0x6229  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x622e  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::AndAlso(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0x6233  ldc.i4.1
0x6234  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6239  dup
0x623a  ldc.i4.0
0x623b  ldloc.2
0x623c  stelem.ref
0x623d  call     T0x2B000092
0x6242  call     T0x2B000093
0x6247  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_RequireIntune(bool)
0x624c  ldloc.1
0x624d  ldarg.0
0x624e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_systemService
0x6253  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0x6258  brtrue.s loc_625D
0x625a  ldc.i4.1
0x625b  br.s     loc_625E
0x625d  ldc.i4.2
0x625e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_ProductType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ProductType)
0x6263  ldloc.1
0x6264  stloc.0
0x6265  ldarg.0
0x6266  ldloc.0
0x6267  callvirt T0x2B000094
0x626c  ret
```
