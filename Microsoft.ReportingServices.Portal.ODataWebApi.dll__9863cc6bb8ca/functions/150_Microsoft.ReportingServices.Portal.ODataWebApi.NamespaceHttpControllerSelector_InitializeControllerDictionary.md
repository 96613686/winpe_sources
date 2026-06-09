# Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::InitializeControllerDictionary

- ea: `0x150`
- end: `0x27b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::InitializeControllerDictionary`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x150`
- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0x150  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x155  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x15a  stloc.0
0x15b  ldarg.0
0x15c  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::_configuration
0x161  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x166  call     class [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver [System.Web.Http]System.Web.Http.ServicesExtensions::GetAssembliesResolver(class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer)
0x16b  stloc.1
0x16c  ldarg.0
0x16d  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::_configuration
0x172  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x177  call     class [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerTypeResolver [System.Web.Http]System.Web.Http.ServicesExtensions::GetHttpControllerTypeResolver(class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer)
0x17c  ldloc.1
0x17d  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Type> [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerTypeResolver::GetControllerTypes(class [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver)
0x182  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>::GetEnumerator()
0x187  stloc.3
0x188  br       loc_23A
0x18d  ldloc.3
0x18e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Type>::get_Current()
0x193  stloc.s  4
0x195  ldloc.s  4
0x197  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x19c  ldc.i4.1
0x19d  newarr   [mscorlib]System.Char
0x1a2  dup
0x1a3  ldc.i4.0
0x1a4  ldsfld   char [mscorlib]System.Type::Delimiter
0x1a9  stelem.i2
0x1aa  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1af  ldloc.s  4
0x1b1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1b6  ldloc.s  4
0x1b8  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1bd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1c2  ldsfld   string [System.Web.Http]System.Web.Http.Dispatcher.DefaultHttpControllerSelector::ControllerSuffix
0x1c7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cc  sub
0x1cd  callvirt instance string [mscorlib]System.String::Remove(int32)
0x1d2  stloc.s  5
0x1d4  dup
0x1d5  ldlen
0x1d6  conv.i4
0x1d7  ldc.i4.2
0x1d8  bge.s    loc_1F3
0x1da  ldstr    aInvalidNamespa// "Invalid namespace detected for namespac"...
0x1df  ldloc.s  4
0x1e1  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x1e6  ldloc.s  5
0x1e8  call     string [mscorlib]System.String::Format(string, object, object)
0x1ed  newobj   instance void [mscorlib]System.IndexOutOfRangeException::.ctor(string)
0x1f2  throw
0x1f3  dup
0x1f4  ldlen
0x1f5  conv.i4
0x1f6  ldc.i4.2
0x1f7  sub
0x1f8  ldelem.ref
0x1f9  ldloc.s  5
0x1fb  call     string Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::GetControllerKey(string versionString, string controllerName)
0x200  stloc.s  6
0x202  ldloc.0
0x203  ldloc.s  6
0x205  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>::ContainsKey(var<u1>)
0x20a  brfalse.s loc_21E
0x20c  ldstr    aAmbiguousRefer// "Ambiguous reference detected for contro"...
0x211  ldloc.s  6
0x213  call     string [mscorlib]System.String::Format(string, object)
0x218  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x21d  throw
0x21e  ldloc.0
0x21f  ldloc.s  6
0x221  ldarg.0
0x222  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::_configuration
0x227  ldloc.s  4
0x229  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x22e  ldloc.s  4
0x230  newobj   instance void [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor::.ctor(class [System.Web.Http]System.Web.Http.HttpConfiguration, string, class [mscorlib]System.Type)
0x235  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>::set_Item(var<u1>, !!T0)
0x23a  ldloc.3
0x23b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x240  brtrue   loc_18D
0x245  leave.s  loc_251
0x247  ldloc.3
0x248  brfalse.s loc_250
0x24a  ldloc.3
0x24b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x250  endfinally
0x251  ldtoken  [Microsoft.AspNet.OData]Microsoft.AspNet.OData.MetadataController
0x256  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25b  stloc.2
0x25c  ldloc.0
0x25d  ldstr    aMetadata// "metadata"
0x262  ldarg.0
0x263  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::_configuration
0x268  ldloc.2
0x269  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x26e  ldloc.2
0x26f  newobj   instance void [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor::.ctor(class [System.Web.Http]System.Web.Http.HttpConfiguration, string, class [mscorlib]System.Type)
0x274  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>::set_Item(var<u1>, !!T0)
0x279  ldloc.0
0x27a  ret
```
