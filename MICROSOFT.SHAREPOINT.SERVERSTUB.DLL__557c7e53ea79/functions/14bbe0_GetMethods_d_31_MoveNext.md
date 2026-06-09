# <GetMethods>d__31::MoveNext

- ea: `0x14bbe0`
- end: `0x14d720`
- name: `<GetMethods>d__31::MoveNext`
- size: `6976`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x6ebc0`
- `0x14bbe0`
- `0x14d740`
- `0x14d7a0`

## string_xrefs

- `0x14c210`: `excludeSecurityGroups`
- `0x14c643`: `excludeSecurityGroups`
- `0x14caf0`: `excludeSecurityGroups`
- `0x14d017`: `excludeSecurityGroups`
- `0x14d528`: `excludeSecurityGroups`
- `0x14c28a`: `retrieveAnonymousLinks`
- `0x14c6bd`: `retrieveAnonymousLinks`
- `0x14cb6a`: `retrieveAnonymousLinks`
- `0x14d091`: `retrieveAnonymousLinks`
- `0x14d5a2`: `retrieveAnonymousLinks`
- `0x14c37e`: `checkForAccessRequests`
- `0x14c7b1`: `checkForAccessRequests`
- `0x14cc5e`: `checkForAccessRequests`
- `0x14d185`: `checkForAccessRequests`
- `0x14d696`: `checkForAccessRequests`

## pseudocode

```c

```

## disassembly

```asm
0x14bbe0  ldarg.0
0x14bbe1  ldfld    int32 <GetMethods>d__31::<>1__state
0x14bbe6  stloc.1
0x14bbe7  ldloc.1
0x14bbe8  switch   loc_14BC1E, loc_14D713, loc_14BC88, loc_14BDF2, loc_14BF49, loc_14C3F6, loc_14C8A3, loc_14CDCA, loc_14D277, loc_14D355, loc_14D70C
0x14bc19  br       loc_14D713
0x14bc1e  ldarg.0
0x14bc1f  ldc.i4.m1
0x14bc20  stfld    int32 <GetMethods>d__31::<>1__state
0x14bc25  ldarg.0
0x14bc26  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__31::proxyContext
0x14bc2b  brtrue.s loc_14BC38
0x14bc2d  ldstr    aProxycontext// "proxyContext"
0x14bc32  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14bc37  throw
0x14bc38  ldarg.0
0x14bc39  ldarg.0
0x14bc3a  ldfld    class Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub <GetMethods>d__31::<>4__this
0x14bc3f  ldarg.0
0x14bc40  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__31::proxyContext
0x14bc45  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::<>n__FabricatedMethod36(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext name)
0x14bc4a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x14bc4f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__31::<>7__wrap34
0x14bc54  ldarg.0
0x14bc55  ldc.i4.1
0x14bc56  stfld    int32 <GetMethods>d__31::<>1__state
0x14bc5b  br.s     loc_14BC8F
0x14bc5d  ldarg.0
0x14bc5e  ldarg.0
0x14bc5f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__31::<>7__wrap34
0x14bc64  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x14bc69  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<itemBase>5__32
0x14bc6e  ldarg.0
0x14bc6f  ldarg.0
0x14bc70  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<itemBase>5__32
0x14bc75  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>2__current
0x14bc7a  ldarg.0
0x14bc7b  ldc.i4.2
0x14bc7c  stfld    int32 <GetMethods>d__31::<>1__state
0x14bc81  ldc.i4.1
0x14bc82  stloc.0
0x14bc83  leave    loc_14D71E
0x14bc88  ldarg.0
0x14bc89  ldc.i4.1
0x14bc8a  stfld    int32 <GetMethods>d__31::<>1__state
0x14bc8f  ldarg.0
0x14bc90  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__31::<>7__wrap34
0x14bc95  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14bc9a  brtrue.s loc_14BC5D
0x14bc9c  ldarg.0
0x14bc9d  call     instance void <GetMethods>d__31::<>m__Finally35()
0x14bca2  ldarg.0
0x14bca3  ldarg.0
0x14bca4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x14bca9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bcae  ldarg.0
0x14bcaf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bcb4  ldstr    aCancurrentuser_12// "CanCurrentUserShare"
0x14bcb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x14bcbe  ldarg.0
0x14bcbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bcc4  ldc.i4.1
0x14bcc5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x14bcca  ldarg.0
0x14bccb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bcd0  ldc.i4.0
0x14bcd1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x14bcd6  ldarg.0
0x14bcd7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bcdc  ldc.i4   0xFFFFFFF
0x14bce1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x14bce6  ldarg.0
0x14bce7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bcec  ldstr    aCancurrentuser_12// "CanCurrentUserShare"
0x14bcf1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x14bcf6  ldarg.0
0x14bcf7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bcfc  ldc.i4.0
0x14bcfd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x14bd02  ldarg.0
0x14bd03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bd08  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.UserSharingCapabilities
0x14bd0d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14bd12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x14bd17  ldarg.0
0x14bd18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bd1d  ldc.i4.1
0x14bd1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14bd23  ldarg.0
0x14bd24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bd29  ldc.i4.0
0x14bd2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x14bd2f  ldarg.0
0x14bd30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bd35  ldc.i4.0
0x14bd36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x14bd3b  ldarg.0
0x14bd3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bd41  ldc.i4.0
0x14bd42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x14bd47  ldarg.0
0x14bd48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bd4d  ldc.i4.0
0x14bd4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x14bd53  ldarg.0
0x14bd54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal0
0x14bd59  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<item>5__33
0x14bd5e  ldarg.0
0x14bd5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<item>5__33
0x14bd64  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x14bd69  ldarg.0
0x14bd6a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x14bd6f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bd74  ldarg.0
0x14bd75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bd7a  ldstr    aDocid// "docId"
0x14bd7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x14bd84  ldarg.0
0x14bd85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bd8a  ldc.i4.0
0x14bd8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x14bd90  ldarg.0
0x14bd91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bd96  ldtoken  [mscorlib]System.String
0x14bd9b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14bda0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x14bda5  ldarg.0
0x14bda6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bdab  ldc.i4.1
0x14bdac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14bdb1  ldarg.0
0x14bdb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bdb7  ldc.i4.0
0x14bdb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x14bdbd  ldarg.0
0x14bdbe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bdc3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x14bdc8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x14bdcd  ldarg.0
0x14bdce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal1
0x14bdd3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x14bdd8  ldarg.0
0x14bdd9  ldarg.0
0x14bdda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<item>5__33
0x14bddf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>2__current
0x14bde4  ldarg.0
0x14bde5  ldc.i4.3
0x14bde6  stfld    int32 <GetMethods>d__31::<>1__state
0x14bdeb  ldc.i4.1
0x14bdec  stloc.0
0x14bded  leave    loc_14D71E
0x14bdf2  ldarg.0
0x14bdf3  ldc.i4.m1
0x14bdf4  stfld    int32 <GetMethods>d__31::<>1__state
0x14bdf9  ldarg.0
0x14bdfa  ldarg.0
0x14bdfb  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x14be00  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be05  ldarg.0
0x14be06  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be0b  ldstr    aCancurrentuser_13// "CanCurrentUserShareRemote"
0x14be10  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x14be15  ldarg.0
0x14be16  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be1b  ldc.i4.1
0x14be1c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x14be21  ldarg.0
0x14be22  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be27  ldc.i4.0
0x14be28  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x14be2d  ldarg.0
0x14be2e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be33  ldc.i4   0xFFFFFFF
0x14be38  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x14be3d  ldarg.0
0x14be3e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be43  ldstr    aCancurrentuser_13// "CanCurrentUserShareRemote"
0x14be48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x14be4d  ldarg.0
0x14be4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be53  ldc.i4.0
0x14be54  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x14be59  ldarg.0
0x14be5a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be5f  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.UserSharingCapabilities
0x14be64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14be69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x14be6e  ldarg.0
0x14be6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be74  ldc.i4.1
0x14be75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14be7a  ldarg.0
0x14be7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be80  ldc.i4.0
0x14be81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x14be86  ldarg.0
0x14be87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be8c  ldc.i4.0
0x14be8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x14be92  ldarg.0
0x14be93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14be98  ldc.i4.0
0x14be99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x14be9e  ldarg.0
0x14be9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14bea4  ldc.i4.0
0x14bea5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x14beaa  ldarg.0
0x14beab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal2
0x14beb0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<item>5__33
0x14beb5  ldarg.0
0x14beb6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<item>5__33
0x14bebb  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x14bec0  ldarg.0
0x14bec1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x14bec6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14becb  ldarg.0
0x14becc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14bed1  ldstr    aDocid// "docId"
0x14bed6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x14bedb  ldarg.0
0x14bedc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14bee1  ldc.i4.0
0x14bee2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x14bee7  ldarg.0
0x14bee8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14beed  ldtoken  [mscorlib]System.String
0x14bef2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14bef7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x14befc  ldarg.0
0x14befd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14bf02  ldc.i4.1
0x14bf03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14bf08  ldarg.0
0x14bf09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14bf0e  ldc.i4.0
0x14bf0f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x14bf14  ldarg.0
0x14bf15  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14bf1a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x14bf1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x14bf24  ldarg.0
0x14bf25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__31::<>g__initLocal3
0x14bf2a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x14bf2f  ldarg.0
0x14bf30  ldarg.0
0x14bf31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<item>5__33
0x14bf36  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>2__current
0x14bf3b  ldarg.0
0x14bf3c  ldc.i4.4
0x14bf3d  stfld    int32 <GetMethods>d__31::<>1__state
0x14bf42  ldc.i4.1
0x14bf43  stloc.0
0x14bf44  leave    loc_14D71E
0x14bf49  ldarg.0
0x14bf4a  ldc.i4.m1
0x14bf4b  stfld    int32 <GetMethods>d__31::<>1__state
0x14bf50  ldarg.0
0x14bf51  ldarg.0
0x14bf52  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x14bf57  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bf5c  ldarg.0
0x14bf5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bf62  ldstr    aGetlistitemsha// "GetListItemSharingInformation"
0x14bf67  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x14bf6c  ldarg.0
0x14bf6d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bf72  ldc.i4.1
0x14bf73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x14bf78  ldarg.0
0x14bf79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bf7e  ldc.i4.0
0x14bf7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x14bf84  ldarg.0
0x14bf85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bf8a  ldc.i4   0xFFFFFFF
0x14bf8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x14bf94  ldarg.0
0x14bf95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bf9a  ldstr    aGetlistitemsha// "GetListItemSharingInformation"
0x14bf9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x14bfa4  ldarg.0
0x14bfa5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bfaa  ldc.i4.0
0x14bfab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x14bfb0  ldarg.0
0x14bfb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bfb6  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation
0x14bfbb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14bfc0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x14bfc5  ldarg.0
0x14bfc6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bfcb  ldc.i4.4
0x14bfcc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14bfd1  ldarg.0
0x14bfd2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
0x14bfd7  ldc.i4.0
0x14bfd8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x14bfdd  ldarg.0
0x14bfde  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__31::<>g__initLocal4
  ... truncated ...
```
