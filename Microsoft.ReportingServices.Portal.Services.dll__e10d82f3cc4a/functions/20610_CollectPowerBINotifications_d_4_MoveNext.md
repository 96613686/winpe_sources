# <CollectPowerBINotifications>d__4::MoveNext

- ea: `0x20610`
- end: `0x20818`
- name: `<CollectPowerBINotifications>d__4::MoveNext`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x20590`
- `0x20610`

## pseudocode

```c

```

## disassembly

```asm
0x20610  ldarg.0
0x20611  ldfld    int32 <CollectPowerBINotifications>d__4::<>1__state
0x20616  stloc.0
0x20617  ldarg.0
0x20618  ldfld    class Microsoft.ReportingServices.Portal.Services.NotificationService <CollectPowerBINotifications>d__4::<>4__this
0x2061d  stloc.1
0x2061e  ldloc.0
0x2061f  brfalse.s loc_2062A
0x20621  ldloc.0
0x20622  ldc.i4.1
0x20623  beq      loc_2080F
0x20628  ldc.i4.0
0x20629  ret
0x2062a  ldarg.0
0x2062b  ldc.i4.m1
0x2062c  stfld    int32 <CollectPowerBINotifications>d__4::<>1__state
0x20631  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x20636  stloc.2
0x20637  ldloc.2
0x20638  ldarg.0
0x20639  ldfld    class Microsoft.ReportingServices.Portal.Services.NotificationService <CollectPowerBINotifications>d__4::<>4__this
0x2063e  stfld    class Microsoft.ReportingServices.Portal.Services.NotificationService <>c__DisplayClass4_0::<>4__this
0x20643  ldloc.2
0x20644  ldarg.0
0x20645  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <CollectPowerBINotifications>d__4::userPrincipal
0x2064a  stfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass4_0::userPrincipal
0x2064f  ldloc.1
0x20650  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService Microsoft.ReportingServices.Portal.Services.NotificationService::_powerBiIntegrationService
0x20655  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService::IsPowerBIEnabled()
0x2065a  brfalse  loc_20816
0x2065f  ldloc.1
0x20660  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService Microsoft.ReportingServices.Portal.Services.NotificationService::_powerBiIntegrationService
0x20665  ldloc.2
0x20666  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass4_0::userPrincipal
0x2066b  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIUserInfo [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService::GetUserInfo(class [mscorlib]System.Security.Principal.IPrincipal)
0x20670  stloc.3
0x20671  ldloc.3
0x20672  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIUserStatus [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIUserInfo::get_Status()
0x20677  ldc.i4.1
0x20678  beq      loc_20816
0x2067d  ldloc.1
0x2067e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.Services.NotificationService::_subscriptionService
0x20683  ldloc.2
0x20684  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass4_0::userPrincipal
0x20689  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::GetSubscriptions(class [mscorlib]System.Security.Principal.IPrincipal)
0x2068e  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription
0x20693  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20698  ldstr    aItem// "item"
0x2069d  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x206a2  stloc.s  4
0x206a4  ldloc.s  4
0x206a6  ldtoken  instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_IsActive()
0x206ab  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x206b0  castclass [mscorlib]System.Reflection.MethodInfo
0x206b5  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x206ba  ldc.i4.1
0x206bb  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x206c0  dup
0x206c1  ldc.i4.0
0x206c2  ldloc.s  4
0x206c4  stelem.ref
0x206c5  call     T0x2B00012D
0x206ca  call     T0x2B00012E
0x206cf  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription
0x206d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x206d9  ldstr    aItem// "item"
0x206de  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x206e3  stloc.s  4
0x206e5  ldloc.1
0x206e6  ldtoken  Microsoft.ReportingServices.Portal.Services.NotificationService
0x206eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x206f0  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x206f5  ldtoken  class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.Services.NotificationService::_subscriptionService
0x206fa  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0x206ff  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0x20704  ldtoken  instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::GetSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x20709  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x2070e  castclass [mscorlib]System.Reflection.MethodInfo
0x20713  ldc.i4.2
0x20714  newarr   [System.Core]System.Linq.Expressions.Expression
0x20719  dup
0x2071a  ldc.i4.0
0x2071b  ldloc.2
0x2071c  ldtoken  <>c__DisplayClass4_0
0x20721  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20726  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x2072b  ldtoken  class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass4_0::userPrincipal
0x20730  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0x20735  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0x2073a  stelem.ref
0x2073b  dup
0x2073c  ldc.i4.1
0x2073d  ldloc.s  4
0x2073f  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Id()
0x20744  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x20749  castclass [mscorlib]System.Reflection.MethodInfo
0x2074e  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x20753  stelem.ref
0x20754  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x20759  ldc.i4.1
0x2075a  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x2075f  dup
0x20760  ldc.i4.0
0x20761  ldloc.s  4
0x20763  stelem.ref
0x20764  call     T0x2B00012F
0x20769  call     T0x2B000130
0x2076e  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription
0x20773  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20778  ldstr    aS// "s"
0x2077d  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x20782  stloc.s  4
0x20784  ldnull
0x20785  ldtoken  valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.KnownDeliveryExtensions Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::KnownAs(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription librarySubscription)
0x2078a  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x2078f  castclass [mscorlib]System.Reflection.MethodInfo
0x20794  ldc.i4.1
0x20795  newarr   [System.Core]System.Linq.Expressions.Expression
0x2079a  dup
0x2079b  ldc.i4.0
0x2079c  ldloc.s  4
0x2079e  stelem.ref
0x2079f  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x207a4  ldtoken  [mscorlib]System.Int32
0x207a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x207ae  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x207b3  ldc.i4.1
0x207b4  box      [mscorlib]System.Int32
0x207b9  ldtoken  [mscorlib]System.Int32
0x207be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x207c3  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x207c8  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::Equal(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0x207cd  ldc.i4.1
0x207ce  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x207d3  dup
0x207d4  ldc.i4.0
0x207d5  ldloc.s  4
0x207d7  stelem.ref
0x207d8  call     T0x2B00012D
0x207dd  call     T0x2B000131
0x207e2  brfalse.s loc_20816
0x207e4  ldloc.3
0x207e5  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIUserStatus [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIUserInfo::get_Status()
0x207ea  ldc.i4.3
0x207eb  beq.s    loc_207F0
0x207ed  ldc.i4.0
0x207ee  br.s     loc_207F1
0x207f0  ldc.i4.1
0x207f1  stloc.s  5
0x207f3  ldarg.0
0x207f4  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Notification::.ctor()
0x207f9  dup
0x207fa  ldloc.s  5
0x207fc  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Notification::set_IssueType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.IssueType)
0x20801  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Notification <CollectPowerBINotifications>d__4::<>2__current
0x20806  ldarg.0
0x20807  ldc.i4.1
0x20808  stfld    int32 <CollectPowerBINotifications>d__4::<>1__state
0x2080d  ldc.i4.1
0x2080e  ret
0x2080f  ldarg.0
0x20810  ldc.i4.m1
0x20811  stfld    int32 <CollectPowerBINotifications>d__4::<>1__state
0x20816  ldc.i4.0
0x20817  ret
```
