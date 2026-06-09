# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::ServiceState

- ea: `0x97a0`
- end: `0x98c6`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::ServiceState`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9a10`
- `0x9a70`

## pseudocode

```c

```

## disassembly

```asm
0x97a0  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::.ctor()
0x97a5  stloc.1
0x97a6  ldloc.1
0x97a7  ldc.i4.1
0x97a8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_IsAvailable(bool)
0x97ad  ldloc.1
0x97ae  ldarg.0
0x97af  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_systemService
0x97b4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetRestrictedFeatures()
0x97b9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_RestrictedFeatures(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x97be  ldloc.1
0x97bf  ldarg.0
0x97c0  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_systemService
0x97c5  ldarg.0
0x97c6  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x97cb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetAllowedSystemActions(class [mscorlib]System.Security.Principal.IPrincipal)
0x97d0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_AllowedSystemActions(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x97d5  ldloc.1
0x97d6  call     string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetTimeZoneFullName()
0x97db  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_TimeZone(string)
0x97e0  ldloc.1
0x97e1  ldarg.0
0x97e2  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_catalogRepository
0x97e7  ldarg.0
0x97e8  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x97ed  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetFavoriteItems(class [mscorlib]System.Security.Principal.IPrincipal)
0x97f2  call     T0x2B000091
0x97f7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_UserHasFavorites(bool)
0x97fc  ldloc.1
0x97fd  ldarg.0
0x97fe  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetAcceptLanguage()
0x9803  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_AcceptLanguage(string)
0x9808  ldloc.1
0x9809  ldarg.0
0x980a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_systemService
0x980f  ldarg.0
0x9810  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x9815  ldc.i4.1
0x9816  newarr   [mscorlib]System.String
0x981b  dup
0x981c  ldc.i4.0
0x981d  ldstr    aRequireintune// "RequireIntune"
0x9822  stelem.ref
0x9823  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetSystemProperties(class [mscorlib]System.Security.Principal.IPrincipal, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x9828  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Property
0x982d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9832  ldstr    aProp// "prop"
0x9837  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x983c  stloc.2
0x983d  ldloc.2
0x983e  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Name()
0x9843  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x9848  castclass [mscorlib]System.Reflection.MethodInfo
0x984d  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x9852  ldstr    aRequireintune// "RequireIntune"
0x9857  ldtoken  [mscorlib]System.String
0x985c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9861  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x9866  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::Equal(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0x986b  ldnull
0x986c  ldtoken  bool [mscorlib]System.Boolean::Parse(string)
0x9871  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x9876  castclass [mscorlib]System.Reflection.MethodInfo
0x987b  ldc.i4.1
0x987c  newarr   [System.Core]System.Linq.Expressions.Expression
0x9881  dup
0x9882  ldc.i4.0
0x9883  ldloc.2
0x9884  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x9889  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x988e  castclass [mscorlib]System.Reflection.MethodInfo
0x9893  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x9898  stelem.ref
0x9899  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x989e  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::AndAlso(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0x98a3  ldc.i4.1
0x98a4  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x98a9  dup
0x98aa  ldc.i4.0
0x98ab  ldloc.2
0x98ac  stelem.ref
0x98ad  call     T0x2B000092
0x98b2  call     T0x2B000093
0x98b7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ServiceState::set_RequireIntune(bool)
0x98bc  ldloc.1
0x98bd  stloc.0
0x98be  ldarg.0
0x98bf  ldloc.0
0x98c0  callvirt T0x2B000094
0x98c5  ret
```
