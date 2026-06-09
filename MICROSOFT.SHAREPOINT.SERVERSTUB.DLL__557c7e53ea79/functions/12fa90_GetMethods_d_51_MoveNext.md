# <GetMethods>d__51::MoveNext

- ea: `0x12fa90`
- end: `0x132fed`
- name: `<GetMethods>d__51::MoveNext`
- size: `13661`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x5b3f0`
- `0x12fa90`
- `0x133010`
- `0x133070`

## string_xrefs

- `0x132ccf`: `Update`
- `0x132d07`: `Update`
- `0x1309c2`: `DeleteObject`
- `0x1309fa`: `Delete`
- `0x12ff3c`: `comment`
- `0x1301ea`: `comment`
- `0x130b66`: `comment`
- `0x132185`: `comment`
- `0x132c3d`: `comment`
- `0x131e90`: `OpenBinaryStream`
- `0x131ec5`: `OpenBinaryStream`
- `0x1316e4`: `GetPreAuthorizedAccessUrl`
- `0x13171c`: `GetPreAuthorizedAccessUrl`
- `0x1310f4`: `GetImagePreviewUri`
- `0x13112c`: `GetImagePreviewUri`
- `0x131f6b`: `OpenBinaryStreamWithOptions`
- `0x131f9f`: `OpenBinaryStreamWithOptions`
- `0x132dad`: `UpdateVirusInfo`
- `0x132de1`: `UpdateVirusInfo`
- `0x131aec`: `MoveTo`
- `0x131b24`: `MoveTo`
- `0x131cf6`: `MoveTo`
- `0x131cbe`: `MoveToUsingPath`
- `0x13061e`: `CopyTo`
- `0x130656`: `CopyTo`
- `0x130828`: `CopyTo`
- `0x1307f0`: `CopyToUsingPath`
- `0x13075e`: `bOverWrite`
- `0x130930`: `bOverWrite`
- `0x1308b6`: `newPath`
- `0x131d84`: `newPath`
- `0x131dfe`: `moveOperations`
- `0x13202d`: `openOptions`

## pseudocode

```c

```

## disassembly

```asm
0x12fa90  ldarg.0
0x12fa91  ldfld    int32 <GetMethods>d__51::<>1__state
0x12fa96  stloc.1
0x12fa97  ldloc.1
0x12fa98  switch   loc_12FB3A, loc_132FE0, loc_12FBA4, loc_12FD0A, loc_12FE5D, loc_12FFB4, loc_13010B, loc_1302DC, loc_1303B9, loc_130605, loc_1307D7, loc_1309A9, loc_130A87, loc_130BDF, loc_130D37, loc_130F83, loc_1310DB, loc_131327, loc_131573, loc_1316CB, loc_131823, loc_13197B, loc_131AD3, loc_131CA5, loc_131E77, loc_131F52, loc_1320A6, loc_1321FE, loc_1322DC, loc_132434, loc_132588, loc_1326DC, loc_1328AE, loc_132A80, loc_132B5E, loc_132CB6, loc_132D94, loc_132FD9
0x12fb35  br       loc_132FE0
0x12fb3a  ldarg.0
0x12fb3b  ldc.i4.m1
0x12fb3c  stfld    int32 <GetMethods>d__51::<>1__state
0x12fb41  ldarg.0
0x12fb42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__51::proxyContext
0x12fb47  brtrue.s loc_12FB54
0x12fb49  ldstr    aProxycontext// "proxyContext"
0x12fb4e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12fb53  throw
0x12fb54  ldarg.0
0x12fb55  ldarg.0
0x12fb56  ldfld    class Microsoft.SharePoint.ServerStub.SPFileServerStub <GetMethods>d__51::<>4__this
0x12fb5b  ldarg.0
0x12fb5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__51::proxyContext
0x12fb61  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPFileServerStub::<>n__FabricatedMethod56(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x12fb66  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x12fb6b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__51::<>7__wrap54
0x12fb70  ldarg.0
0x12fb71  ldc.i4.1
0x12fb72  stfld    int32 <GetMethods>d__51::<>1__state
0x12fb77  br.s     loc_12FBAB
0x12fb79  ldarg.0
0x12fb7a  ldarg.0
0x12fb7b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__51::<>7__wrap54
0x12fb80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x12fb85  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<itemBase>5__52
0x12fb8a  ldarg.0
0x12fb8b  ldarg.0
0x12fb8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<itemBase>5__52
0x12fb91  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>2__current
0x12fb96  ldarg.0
0x12fb97  ldc.i4.2
0x12fb98  stfld    int32 <GetMethods>d__51::<>1__state
0x12fb9d  ldc.i4.1
0x12fb9e  stloc.0
0x12fb9f  leave    loc_132FEB
0x12fba4  ldarg.0
0x12fba5  ldc.i4.1
0x12fba6  stfld    int32 <GetMethods>d__51::<>1__state
0x12fbab  ldarg.0
0x12fbac  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__51::<>7__wrap54
0x12fbb1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12fbb6  brtrue.s loc_12FB79
0x12fbb8  ldarg.0
0x12fbb9  call     instance void <GetMethods>d__51::<>m__Finally55()
0x12fbbe  ldarg.0
0x12fbbf  ldarg.0
0x12fbc0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x12fbc5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fbca  ldarg.0
0x12fbcb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fbd0  ldstr    aAddactivities// "AddActivities"
0x12fbd5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12fbda  ldarg.0
0x12fbdb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fbe0  ldc.i4.0
0x12fbe1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x12fbe6  ldarg.0
0x12fbe7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fbec  ldc.i4.0
0x12fbed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x12fbf2  ldarg.0
0x12fbf3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fbf8  ldc.i4.8
0x12fbf9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x12fbfe  ldarg.0
0x12fbff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc04  ldstr    aAddactivities// "AddActivities"
0x12fc09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x12fc0e  ldarg.0
0x12fc0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc14  ldc.i4.0
0x12fc15  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12fc1a  ldarg.0
0x12fc1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc20  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityResponse>
0x12fc25  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12fc2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x12fc2f  ldarg.0
0x12fc30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc35  ldc.i4.3
0x12fc36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12fc3b  ldarg.0
0x12fc3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc41  ldc.i4.0
0x12fc42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x12fc47  ldarg.0
0x12fc48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc4d  ldc.i4.0
0x12fc4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x12fc53  ldarg.0
0x12fc54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc59  ldc.i4.0
0x12fc5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x12fc5f  ldarg.0
0x12fc60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc65  ldc.i4.1
0x12fc66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x12fc6b  ldarg.0
0x12fc6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal0
0x12fc71  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<item>5__53
0x12fc76  ldarg.0
0x12fc77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<item>5__53
0x12fc7c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x12fc81  ldarg.0
0x12fc82  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x12fc87  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fc8c  ldarg.0
0x12fc8d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fc92  ldstr    aActivities_0// "activities"
0x12fc97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x12fc9c  ldarg.0
0x12fc9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fca2  ldc.i4.0
0x12fca3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x12fca8  ldarg.0
0x12fca9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fcae  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityRequest>
0x12fcb3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12fcb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x12fcbd  ldarg.0
0x12fcbe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fcc3  ldc.i4.3
0x12fcc4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12fcc9  ldarg.0
0x12fcca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fccf  ldc.i4.0
0x12fcd0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x12fcd5  ldarg.0
0x12fcd6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fcdb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x12fce0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x12fce5  ldarg.0
0x12fce6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal1
0x12fceb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x12fcf0  ldarg.0
0x12fcf1  ldarg.0
0x12fcf2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<item>5__53
0x12fcf7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>2__current
0x12fcfc  ldarg.0
0x12fcfd  ldc.i4.3
0x12fcfe  stfld    int32 <GetMethods>d__51::<>1__state
0x12fd03  ldc.i4.1
0x12fd04  stloc.0
0x12fd05  leave    loc_132FEB
0x12fd0a  ldarg.0
0x12fd0b  ldc.i4.m1
0x12fd0c  stfld    int32 <GetMethods>d__51::<>1__state
0x12fd11  ldarg.0
0x12fd12  ldarg.0
0x12fd13  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x12fd18  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd1d  ldarg.0
0x12fd1e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd23  ldstr    aAddclientactiv// "AddClientActivities"
0x12fd28  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12fd2d  ldarg.0
0x12fd2e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd33  ldc.i4.0
0x12fd34  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x12fd39  ldarg.0
0x12fd3a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd3f  ldc.i4.0
0x12fd40  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x12fd45  ldarg.0
0x12fd46  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd4b  ldc.i4.8
0x12fd4c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x12fd51  ldarg.0
0x12fd52  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd57  ldstr    aAddclientactiv// "AddClientActivities"
0x12fd5c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x12fd61  ldarg.0
0x12fd62  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd67  ldc.i4.0
0x12fd68  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12fd6d  ldarg.0
0x12fd6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd73  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityResponse>
0x12fd78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12fd7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x12fd82  ldarg.0
0x12fd83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd88  ldc.i4.3
0x12fd89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12fd8e  ldarg.0
0x12fd8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fd94  ldc.i4.0
0x12fd95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x12fd9a  ldarg.0
0x12fd9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fda0  ldc.i4.0
0x12fda1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x12fda6  ldarg.0
0x12fda7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fdac  ldc.i4.0
0x12fdad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x12fdb2  ldarg.0
0x12fdb3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fdb8  ldc.i4.1
0x12fdb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x12fdbe  ldarg.0
0x12fdbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal2
0x12fdc4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<item>5__53
0x12fdc9  ldarg.0
0x12fdca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<item>5__53
0x12fdcf  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x12fdd4  ldarg.0
0x12fdd5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x12fdda  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fddf  ldarg.0
0x12fde0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fde5  ldstr    aActivitiesstre// "activitiesStream"
0x12fdea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x12fdef  ldarg.0
0x12fdf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fdf5  ldc.i4.0
0x12fdf6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x12fdfb  ldarg.0
0x12fdfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fe01  ldtoken  [mscorlib]System.IO.Stream
0x12fe06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12fe0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x12fe10  ldarg.0
0x12fe11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fe16  ldc.i4.0
0x12fe17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12fe1c  ldarg.0
0x12fe1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fe22  ldc.i4.0
0x12fe23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x12fe28  ldarg.0
0x12fe29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fe2e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x12fe33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x12fe38  ldarg.0
0x12fe39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__51::<>g__initLocal3
0x12fe3e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x12fe43  ldarg.0
0x12fe44  ldarg.0
0x12fe45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<item>5__53
0x12fe4a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>2__current
0x12fe4f  ldarg.0
0x12fe50  ldc.i4.4
0x12fe51  stfld    int32 <GetMethods>d__51::<>1__state
0x12fe56  ldc.i4.1
0x12fe57  stloc.0
0x12fe58  leave    loc_132FEB
0x12fe5d  ldarg.0
0x12fe5e  ldc.i4.m1
0x12fe5f  stfld    int32 <GetMethods>d__51::<>1__state
0x12fe64  ldarg.0
0x12fe65  ldarg.0
0x12fe66  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x12fe6b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12fe70  ldarg.0
0x12fe71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12fe76  ldstr    aApprove// "Approve"
0x12fe7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12fe80  ldarg.0
0x12fe81  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12fe86  ldc.i4.0
0x12fe87  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x12fe8c  ldarg.0
0x12fe8d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12fe92  ldc.i4.0
0x12fe93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x12fe98  ldarg.0
0x12fe99  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12fe9e  ldc.i4   0xFFFFFFF
0x12fea3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x12fea8  ldarg.0
0x12fea9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12feae  ldstr    aApprove// "Approve"
0x12feb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x12feb8  ldarg.0
0x12feb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12febe  ldc.i4.0
0x12febf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12fec4  ldarg.0
0x12fec5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12feca  ldtoken  [mscorlib]System.Void
0x12fecf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12fed4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x12fed9  ldarg.0
0x12feda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12fedf  ldc.i4.0
0x12fee0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12fee5  ldarg.0
0x12fee6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
0x12feeb  ldc.i4.0
0x12feec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x12fef1  ldarg.0
0x12fef2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__51::<>g__initLocal4
  ... truncated ...
```
