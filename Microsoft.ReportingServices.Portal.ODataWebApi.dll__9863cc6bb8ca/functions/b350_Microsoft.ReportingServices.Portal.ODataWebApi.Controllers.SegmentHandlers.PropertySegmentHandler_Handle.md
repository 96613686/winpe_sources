# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.PropertySegmentHandler::Handle

- ea: `0xb350`
- end: `0xb414`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.PropertySegmentHandler::Handle`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xb350`
- `0xf1c0`

## pseudocode

```c

```

## disassembly

```asm
0xb350  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xb355  stloc.0
0xb356  ldloc.0
0xb357  ldnull
0xb358  stfld    string <>c__DisplayClass0_0::propertyName
0xb35d  ldarg.2
0xb35e  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment
0xb363  stloc.1
0xb364  ldloc.1
0xb365  brfalse.s loc_B378
0xb367  ldloc.0
0xb368  ldloc.1
0xb369  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0xb36e  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0xb373  stfld    string <>c__DisplayClass0_0::propertyName
0xb378  ldarg.2
0xb379  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.PropertySegment
0xb37e  stloc.2
0xb37f  ldloc.2
0xb380  brfalse.s loc_B393
0xb382  ldloc.0
0xb383  ldloc.2
0xb384  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.PropertySegment::get_Property()
0xb389  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0xb38e  stfld    string <>c__DisplayClass0_0::propertyName
0xb393  ldloc.0
0xb394  ldfld    string <>c__DisplayClass0_0::propertyName
0xb399  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb39e  brfalse.s loc_B3AB
0xb3a0  ldstr    aPropertynameCa// "PropertyName cannot be null or empty"
0xb3a5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb3aa  throw
0xb3ab  ldarg.1
0xb3ac  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb3b1  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0xb3b6  ldloc.0
0xb3b7  ldftn    instance bool <>c__DisplayClass0_0::<Handle>b__0(class [mscorlib]System.Reflection.PropertyInfo p)
0xb3bd  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, bool>::.ctor(object, native int)
0xb3c2  call     T0x2B0000EF
0xb3c7  stloc.3
0xb3c8  ldloc.3
0xb3c9  ldnull
0xb3ca  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Equality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0xb3cf  brfalse.s loc_B3D3
0xb3d1  ldnull
0xb3d2  ret
0xb3d3  nop
0xb3d4  ldloc.3
0xb3d5  ldarg.1
0xb3d6  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0xb3db  stloc.s  4
0xb3dd  leave.s  loc_B411
0xb3df  stloc.s  5
0xb3e1  ldloc.s  5
0xb3e3  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xb3e8  brfalse.s loc_B40E
0xb3ea  ldloc.s  5
0xb3ec  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xb3f1  isinst   [System.Web.Http]System.Web.Http.HttpResponseException
0xb3f6  stloc.s  6
0xb3f8  ldloc.s  6
0xb3fa  brfalse.s loc_B40E
0xb3fc  ldloc.s  6
0xb3fe  callvirt instance class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.Http]System.Web.Http.HttpResponseException::get_Response()
0xb403  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0xb408  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xb40d  throw
0xb40e  ldloc.s  5
0xb410  throw
0xb411  ldloc.s  4
0xb413  ret
```
