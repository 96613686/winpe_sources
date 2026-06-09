# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::GetRoot

- ea: `0xb4d0`
- end: `0xb6bc`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::GetRoot`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xb4d0`

## string_xrefs

- `0xb6a6`: `No entityset handler for path '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0xb4d0  ldarg.1
0xb4d1  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xb4d6  ldstr    aEntitysetKeyCa// "~/entityset/key/cast"
0xb4db  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xb4e0  brfalse  loc_B574
0xb4e5  newobj   instance void class <>c__DisplayClass9_0<var<u1>>::.ctor()
0xb4ea  stloc.0
0xb4eb  ldloc.0
0xb4ec  ldarg.1
0xb4ed  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseEntitySetName(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xb4f2  stfld    string class <>c__DisplayClass9_0<var<u1>>::entitySetName
0xb4f7  ldloc.0
0xb4f8  ldarg.1
0xb4f9  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xb4fe  ldc.i4.1
0xb4ff  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xb504  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment
0xb509  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>> [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment::get_Keys()
0xb50e  call     T0x2B0000F0
0xb513  stloc.1
0xb514  ldloca.s 1
0xb516  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0xb51b  callvirt instance string [mscorlib]System.Object::ToString()
0xb520  stfld    string class <>c__DisplayClass9_0<var<u1>>::key
0xb525  ldloc.0
0xb526  ldarg.1
0xb527  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xb52c  ldc.i4.2
0xb52d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xb532  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.TypeSegment
0xb537  callvirt instance string [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment::get_Identifier()
0xb53c  stfld    string class <>c__DisplayClass9_0<var<u1>>::cast
0xb541  ldarg.0
0xb542  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb547  ldc.i4.4
0xb548  ldloc.0
0xb549  ldftn    instance string class <>c__DisplayClass9_0<var<u1>>::<GetRoot>b__0()
0xb54f  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb554  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb559  ldarg.2
0xb55a  ldc.i4.2
0xb55b  stind.i4
0xb55c  ldarg.0
0xb55d  ldloc.0
0xb55e  ldfld    string class <>c__DisplayClass9_0<var<u1>>::key
0xb563  ldloc.0
0xb564  ldfld    string class <>c__DisplayClass9_0<var<u1>>::cast
0xb569  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::GetEntity(!!T0, string)
0xb56e  box      var<u1>
0xb573  ret
0xb574  ldarg.1
0xb575  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xb57a  ldstr    aEntitysetKey// "~/entityset/key"
0xb57f  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xb584  brfalse.s loc_B5F4
0xb586  newobj   instance void class <>c__DisplayClass9_1<var<u1>>::.ctor()
0xb58b  stloc.2
0xb58c  ldloc.2
0xb58d  ldarg.1
0xb58e  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseEntitySetName(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xb593  stfld    string class <>c__DisplayClass9_1<var<u1>>::entitySetName
0xb598  ldloc.2
0xb599  ldarg.1
0xb59a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xb59f  ldc.i4.1
0xb5a0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xb5a5  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment
0xb5aa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>> [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment::get_Keys()
0xb5af  call     T0x2B0000F0
0xb5b4  stloc.1
0xb5b5  ldloca.s 1
0xb5b7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0xb5bc  callvirt instance string [mscorlib]System.Object::ToString()
0xb5c1  stfld    string class <>c__DisplayClass9_1<var<u1>>::key
0xb5c6  ldarg.0
0xb5c7  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb5cc  ldc.i4.4
0xb5cd  ldloc.2
0xb5ce  ldftn    instance string class <>c__DisplayClass9_1<var<u1>>::<GetRoot>b__1()
0xb5d4  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb5d9  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb5de  ldarg.2
0xb5df  ldc.i4.2
0xb5e0  stind.i4
0xb5e1  ldarg.0
0xb5e2  ldloc.2
0xb5e3  ldfld    string class <>c__DisplayClass9_1<var<u1>>::key
0xb5e8  ldnull
0xb5e9  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::GetEntity(!!T0, string)
0xb5ee  box      var<u1>
0xb5f3  ret
0xb5f4  ldarg.1
0xb5f5  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xb5fa  ldstr    aEntitysetCast// "~/entityset/cast"
0xb5ff  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xb604  brfalse.s loc_B65C
0xb606  newobj   instance void class <>c__DisplayClass9_2<var<u1>>::.ctor()
0xb60b  stloc.3
0xb60c  ldloc.3
0xb60d  ldarg.1
0xb60e  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseEntitySetName(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xb613  stfld    string class <>c__DisplayClass9_2<var<u1>>::entitySetName
0xb618  ldloc.3
0xb619  ldarg.1
0xb61a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xb61f  ldc.i4.1
0xb620  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xb625  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.TypeSegment
0xb62a  callvirt instance string [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment::get_Identifier()
0xb62f  stfld    string class <>c__DisplayClass9_2<var<u1>>::cast
0xb634  ldarg.0
0xb635  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb63a  ldc.i4.4
0xb63b  ldloc.3
0xb63c  ldftn    instance string class <>c__DisplayClass9_2<var<u1>>::<GetRoot>b__2()
0xb642  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb647  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb64c  ldarg.2
0xb64d  ldc.i4.1
0xb64e  stind.i4
0xb64f  ldarg.0
0xb650  ldloc.3
0xb651  ldfld    string class <>c__DisplayClass9_2<var<u1>>::cast
0xb656  callvirt instance class [System.Core]System.Linq.IQueryable`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::GetEntitySet(!!T0)
0xb65b  ret
0xb65c  ldarg.1
0xb65d  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xb662  ldstr    aEntityset// "~/entityset"
0xb667  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xb66c  brfalse.s loc_B6A6
0xb66e  newobj   instance void class <>c__DisplayClass9_3<var<u1>>::.ctor()
0xb673  stloc.s  4
0xb675  ldloc.s  4
0xb677  ldarg.1
0xb678  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseEntitySetName(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xb67d  stfld    string class <>c__DisplayClass9_3<var<u1>>::entitySetName
0xb682  ldarg.0
0xb683  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb688  ldc.i4.4
0xb689  ldloc.s  4
0xb68b  ldftn    instance string class <>c__DisplayClass9_3<var<u1>>::<GetRoot>b__3()
0xb691  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb696  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb69b  ldarg.2
0xb69c  ldc.i4.1
0xb69d  stind.i4
0xb69e  ldarg.0
0xb69f  ldnull
0xb6a0  callvirt instance class [System.Core]System.Linq.IQueryable`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::GetEntitySet(!!T0)
0xb6a5  ret
0xb6a6  ldstr    aNoEntitysetHan// "No entityset handler for path '{0}'"
0xb6ab  ldarg.1
0xb6ac  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xb6b1  call     string [mscorlib]System.String::Format(string, object)
0xb6b6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb6bb  throw
```
