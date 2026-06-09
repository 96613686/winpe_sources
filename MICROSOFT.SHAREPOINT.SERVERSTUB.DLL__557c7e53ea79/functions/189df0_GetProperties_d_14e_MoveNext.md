# <GetProperties>d__14e::MoveNext

- ea: `0x189df0`
- end: `0x18fb91`
- name: `<GetProperties>d__14e::MoveNext`
- size: `23969`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9b910`
- `0x189df0`
- `0x18fbc0`
- `0x18fc20`

## string_xrefs

- `0x18b788`: `Created`
- `0x18b802`: `Created`
- `0x18b86f`: `CurrentChangeToken`
- `0x18b8dc`: `CurrentChangeToken`
- `0x18e1ea`: `ServerRelativePath`
- `0x18e257`: `ServerRelativePath`
- `0x18f90b`: `WelcomePage`
- `0x18f978`: `WelcomePage`
- `0x18d878`: `ResourcePath`
- `0x18b411`: `CommentsOnSitePagesDisabled`
- `0x18b483`: `CommentsOnSitePagesDisabled`
- `0x18f3ea`: `UIVersionConfigurationEnabled`
- `0x18f45c`: `UIVersionConfigurationEnabled`
- `0x18f831`: `WebTemplate`
- `0x18f89e`: `WebTemplate`
- `0x18b4f0`: `Configuration`
- `0x18b562`: `Configuration`
- `0x18a3b5`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x18a427`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x18a650`: `AllowRevertFromTemplateForCurrentUser`
- `0x18a6c2`: `AllowRevertFromTemplateForCurrentUser`
- `0x18a80e`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x18a880`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x18cfdb`: `ListTemplates`
- `0x18d048`: `ListTemplates`
- `0x18d6bf`: `OverwriteTranslationsOnChange`
- `0x18d731`: `OverwriteTranslationsOnChange`
- `0x18de7d`: `RequestAccessEmail`
- `0x18deea`: `RequestAccessEmail`
- `0x18e10b`: `SaveSiteAsTemplateEnabled`
- `0x18e17d`: `SaveSiteAsTemplateEnabled`
- `0x18fabf`: `WorkflowTemplates`
- `0x18fb2c`: `WorkflowTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x189df0  ldarg.0
0x189df1  ldfld    int32 <GetProperties>d__14e::<>1__state
0x189df6  stloc.1
0x189df7  ldloc.1
0x189df8  switch   loc_189FB6, loc_18FB84, loc_18A020, loc_18A10C, loc_18A1E5, loc_18A2BE, loc_18A39C, loc_18A47A, loc_18A558, loc_18A637, loc_18A716, loc_18A7F5, loc_18A8D4, loc_18A9B3, loc_18AA8D, loc_18AB67, loc_18AC4E, loc_18AD28, loc_18AE02, loc_18AEDC, loc_18AFB6, loc_18B090, loc_18B16A, loc_18B244, loc_18B31E, loc_18B3F8, loc_18B4D7, loc_18B5B6, loc_18B695, loc_18B76F, loc_18B856, loc_18B930, loc_18BA0A, loc_18BAE4, loc_18BBBE, loc_18BC98, loc_18BD72, loc_18BE4C, loc_18BF26, loc_18C00E, loc_18C0ED, loc_18C1CC, loc_18C2AB, loc_18C385, loc_18C464, loc_18C53E, loc_18C61D, loc_18C6F7, loc_18C7D1, loc_18C8AB, loc_18C98A, loc_18CA69, loc_18CB51 \
0x189fb1  br       loc_18FB84
0x189fb6  ldarg.0
0x189fb7  ldc.i4.m1
0x189fb8  stfld    int32 <GetProperties>d__14e::<>1__state
0x189fbd  ldarg.0
0x189fbe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__14e::proxyContext
0x189fc3  brtrue.s loc_189FD0
0x189fc5  ldstr    aProxycontext// "proxyContext"
0x189fca  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x189fcf  throw
0x189fd0  ldarg.0
0x189fd1  ldarg.0
0x189fd2  ldfld    class Microsoft.SharePoint.ServerStub.SPWebServerStub <GetProperties>d__14e::<>4__this
0x189fd7  ldarg.0
0x189fd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__14e::proxyContext
0x189fdd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPWebServerStub::<>n__FabricatedMethod152(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x189fe2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x189fe7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__14e::<>7__wrap150
0x189fec  ldarg.0
0x189fed  ldc.i4.1
0x189fee  stfld    int32 <GetProperties>d__14e::<>1__state
0x189ff3  br.s     loc_18A027
0x189ff5  ldarg.0
0x189ff6  ldarg.0
0x189ff7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__14e::<>7__wrap150
0x189ffc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x18a001  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<item>5__14f
0x18a006  ldarg.0
0x18a007  ldarg.0
0x18a008  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<item>5__14f
0x18a00d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>2__current
0x18a012  ldarg.0
0x18a013  ldc.i4.2
0x18a014  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a019  ldc.i4.1
0x18a01a  stloc.0
0x18a01b  leave    loc_18FB8F
0x18a020  ldarg.0
0x18a021  ldc.i4.1
0x18a022  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a027  ldarg.0
0x18a028  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__14e::<>7__wrap150
0x18a02d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18a032  brtrue.s loc_189FF5
0x18a034  ldarg.0
0x18a035  call     instance void <GetProperties>d__14e::<>m__Finally151()
0x18a03a  ldarg.0
0x18a03b  ldarg.0
0x18a03c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x18a041  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a046  ldarg.0
0x18a047  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a04c  ldstr    aActivities// "Activities"
0x18a051  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x18a056  ldarg.0
0x18a057  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a05c  ldc.i4.0
0x18a05d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x18a062  ldarg.0
0x18a063  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a068  ldc.i4.5
0x18a069  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18a06e  ldarg.0
0x18a06f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a074  ldc.i4.1
0x18a075  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x18a07a  ldarg.0
0x18a07b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a080  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet
0x18a085  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18a08a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x18a08f  ldarg.0
0x18a090  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a095  ldc.i4.1
0x18a096  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x18a09b  ldarg.0
0x18a09c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0a1  ldc.i4.1
0x18a0a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x18a0a7  ldarg.0
0x18a0a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0ad  ldnull
0x18a0ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x18a0b3  ldarg.0
0x18a0b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0b9  ldstr    aActivities// "Activities"
0x18a0be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x18a0c3  ldarg.0
0x18a0c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0c9  ldnull
0x18a0ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x18a0cf  ldarg.0
0x18a0d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0d5  ldc.i4.0
0x18a0d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18a0db  ldarg.0
0x18a0dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0e1  ldc.i4.1
0x18a0e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x18a0e7  ldarg.0
0x18a0e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0ed  ldc.i4.0
0x18a0ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x18a0f3  ldarg.0
0x18a0f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale4
0x18a0f9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>2__current
0x18a0fe  ldarg.0
0x18a0ff  ldc.i4.3
0x18a100  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a105  ldc.i4.1
0x18a106  stloc.0
0x18a107  leave    loc_18FB8F
0x18a10c  ldarg.0
0x18a10d  ldc.i4.m1
0x18a10e  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a113  ldarg.0
0x18a114  ldarg.0
0x18a115  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x18a11a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a11f  ldarg.0
0x18a120  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a125  ldstr    aActivitylogger// "ActivityLogger"
0x18a12a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x18a12f  ldarg.0
0x18a130  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a135  ldc.i4.0
0x18a136  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x18a13b  ldarg.0
0x18a13c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a141  ldc.i4.4
0x18a142  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18a147  ldarg.0
0x18a148  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a14d  ldc.i4.0
0x18a14e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x18a153  ldarg.0
0x18a154  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a159  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPActivityLogger
0x18a15e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18a163  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x18a168  ldarg.0
0x18a169  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a16e  ldc.i4.1
0x18a16f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x18a174  ldarg.0
0x18a175  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a17a  ldc.i4.1
0x18a17b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x18a180  ldarg.0
0x18a181  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a186  ldnull
0x18a187  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x18a18c  ldarg.0
0x18a18d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a192  ldstr    aActivitylogger// "ActivityLogger"
0x18a197  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x18a19c  ldarg.0
0x18a19d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a1a2  ldnull
0x18a1a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x18a1a8  ldarg.0
0x18a1a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a1ae  ldc.i4.0
0x18a1af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18a1b4  ldarg.0
0x18a1b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a1ba  ldc.i4.0
0x18a1bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x18a1c0  ldarg.0
0x18a1c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a1c6  ldc.i4.0
0x18a1c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x18a1cc  ldarg.0
0x18a1cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale5
0x18a1d2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>2__current
0x18a1d7  ldarg.0
0x18a1d8  ldc.i4.4
0x18a1d9  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a1de  ldc.i4.1
0x18a1df  stloc.0
0x18a1e0  leave    loc_18FB8F
0x18a1e5  ldarg.0
0x18a1e6  ldc.i4.m1
0x18a1e7  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a1ec  ldarg.0
0x18a1ed  ldarg.0
0x18a1ee  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x18a1f3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a1f8  ldarg.0
0x18a1f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a1fe  ldstr    aAlerts// "Alerts"
0x18a203  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x18a208  ldarg.0
0x18a209  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a20e  ldc.i4.0
0x18a20f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x18a214  ldarg.0
0x18a215  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a21a  ldc.i4.5
0x18a21b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18a220  ldarg.0
0x18a221  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a226  ldc.i4.1
0x18a227  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x18a22c  ldarg.0
0x18a22d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a232  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPAlertCollection
0x18a237  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18a23c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x18a241  ldarg.0
0x18a242  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a247  ldc.i4.1
0x18a248  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x18a24d  ldarg.0
0x18a24e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a253  ldc.i4.1
0x18a254  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x18a259  ldarg.0
0x18a25a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a25f  ldnull
0x18a260  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x18a265  ldarg.0
0x18a266  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a26b  ldstr    aAlerts// "Alerts"
0x18a270  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x18a275  ldarg.0
0x18a276  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a27b  ldnull
0x18a27c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x18a281  ldarg.0
0x18a282  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a287  ldc.i4.0
0x18a288  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18a28d  ldarg.0
0x18a28e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a293  ldc.i4.0
0x18a294  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x18a299  ldarg.0
0x18a29a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a29f  ldc.i4.0
0x18a2a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x18a2a5  ldarg.0
0x18a2a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale6
0x18a2ab  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>2__current
0x18a2b0  ldarg.0
0x18a2b1  ldc.i4.5
0x18a2b2  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a2b7  ldc.i4.1
0x18a2b8  stloc.0
0x18a2b9  leave    loc_18FB8F
0x18a2be  ldarg.0
0x18a2bf  ldc.i4.m1
0x18a2c0  stfld    int32 <GetProperties>d__14e::<>1__state
0x18a2c5  ldarg.0
0x18a2c6  ldarg.0
0x18a2c7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x18a2cc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a2d1  ldarg.0
0x18a2d2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a2d7  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x18a2dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x18a2e1  ldarg.0
0x18a2e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a2e7  ldc.i4.0
0x18a2e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x18a2ed  ldarg.0
0x18a2ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a2f3  ldc.i4.1
0x18a2f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18a2f9  ldarg.0
0x18a2fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a2ff  ldc.i4.1
0x18a300  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x18a305  ldarg.0
0x18a306  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a30b  ldtoken  [mscorlib]System.Boolean
0x18a310  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18a315  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x18a31a  ldarg.0
0x18a31b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a320  ldc.i4.0
0x18a321  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x18a326  ldarg.0
0x18a327  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a32c  ldc.i4.1
0x18a32d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x18a332  ldarg.0
0x18a333  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a338  ldc.i4.0
0x18a339  box      [mscorlib]System.Boolean
0x18a33e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x18a343  ldarg.0
0x18a344  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__14e::<>g__initLocale7
0x18a349  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x18a34e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
