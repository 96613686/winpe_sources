# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::RegisterModel

- ea: `0x93c0`
- end: `0x94de`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::RegisterModel`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd0`
- `0x5fb0`

## callees

- `0x93c0`

## pseudocode

```c

```

## disassembly

```asm
0x93c0  ldarg.0
0x93c1  callvirt T0x2B0000CA
0x93c6  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource
0x93cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93d0  ldstr    aX// "x"
0x93d5  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x93da  stloc.0
0x93db  ldloc.0
0x93dc  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::get_PackageId()
0x93e1  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x93e6  castclass [mscorlib]System.Reflection.MethodInfo
0x93eb  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x93f0  ldc.i4.1
0x93f1  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x93f6  dup
0x93f7  ldc.i4.0
0x93f8  ldloc.0
0x93f9  stelem.ref
0x93fa  call     T0x2B0000CB
0x93ff  callvirt T0x2B0000CC
0x9404  ldarg.0
0x9405  callvirt T0x2B0000CD
0x940a  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceItem
0x940f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9414  ldstr    aX// "x"
0x9419  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x941e  stloc.0
0x941f  ldloc.0
0x9420  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceItem::get_TypeName()
0x9425  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x942a  castclass [mscorlib]System.Reflection.MethodInfo
0x942f  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x9434  ldc.i4.1
0x9435  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x943a  dup
0x943b  ldc.i4.0
0x943c  ldloc.0
0x943d  stelem.ref
0x943e  call     T0x2B0000CE
0x9443  callvirt T0x2B0000CF
0x9448  ldarg.0
0x9449  callvirt T0x2B0000CD
0x944e  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceItem
0x9453  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9458  ldstr    aX// "x"
0x945d  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x9462  stloc.0
0x9463  ldloc.0
0x9464  ldtoken  instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceItem::get_IsEmbedded()
0x9469  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x946e  castclass [mscorlib]System.Reflection.MethodInfo
0x9473  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x9478  ldc.i4.1
0x9479  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x947e  dup
0x947f  ldc.i4.0
0x9480  ldloc.0
0x9481  stelem.ref
0x9482  call     T0x2B0000D0
0x9487  callvirt T0x2B0000D1
0x948c  ldarg.0
0x948d  callvirt T0x2B0000D2
0x9492  pop
0x9493  ldarg.0
0x9494  callvirt T0x2B0000D2
0x9499  ldc.i4.1
0x949a  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceType>::Member(var<u1>)
0x949f  pop
0x94a0  ldarg.0
0x94a1  ldstr    aSystemresource_2// "SystemResources"
0x94a6  callvirt T0x2B0000D3
0x94ab  pop
0x94ac  ldarg.0
0x94ad  ldstr    aSystemresource_3// "SystemResourceItems"
0x94b2  callvirt T0x2B0000D4
0x94b7  pop
0x94b8  ldarg.0
0x94b9  ldsfld   class [mscorlib]System.Action`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder> <>c::<>9__7_3
0x94be  dup
0x94bf  brtrue.s loc_94D8
0x94c1  pop
0x94c2  ldsfld   class <>c <>c::<>9
0x94c7  ldftn    instance void <>c::<RegisterModel>b__7_3(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder b)
0x94cd  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder>::.ctor(object, native int)
0x94d2  dup
0x94d3  stsfld   class [mscorlib]System.Action`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder> <>c::<>9__7_3
0x94d8  callvirt instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder::set_OnModelCreating(class [mscorlib]System.Action`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder>)
0x94dd  ret
```
