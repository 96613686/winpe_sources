# <GetProperties>d__15::MoveNext

- ea: `0x1e2a0`
- end: `0x1ea52`
- name: `<GetProperties>d__15::MoveNext`
- size: `1970`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x9310`
- `0x1e2a0`
- `0x1ea80`
- `0x1eae0`

## pseudocode

```c

```

## disassembly

```asm
0x1e2a0  ldarg.0
0x1e2a1  ldfld    int32 <GetProperties>d__15::<>1__state
0x1e2a6  stloc.1
0x1e2a7  ldloc.1
0x1e2a8  switch   loc_1E2DE, loc_1EA45, loc_1E348, loc_1E439, loc_1E517, loc_1E5F5, loc_1E6CE, loc_1E7A7, loc_1E880, loc_1E967, loc_1EA3E
0x1e2d9  br       loc_1EA45
0x1e2de  ldarg.0
0x1e2df  ldc.i4.m1
0x1e2e0  stfld    int32 <GetProperties>d__15::<>1__state
0x1e2e5  ldarg.0
0x1e2e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__15::proxyContext
0x1e2eb  brtrue.s loc_1E2F8
0x1e2ed  ldstr    aProxycontext// "proxyContext"
0x1e2f2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1e2f7  throw
0x1e2f8  ldarg.0
0x1e2f9  ldarg.0
0x1e2fa  ldfld    class Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub <GetProperties>d__15::<>4__this
0x1e2ff  ldarg.0
0x1e300  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__15::proxyContext
0x1e305  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::<>n__FabricatedMethod19(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1e30a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1e30f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__15::<>7__wrap17
0x1e314  ldarg.0
0x1e315  ldc.i4.1
0x1e316  stfld    int32 <GetProperties>d__15::<>1__state
0x1e31b  br.s     loc_1E34F
0x1e31d  ldarg.0
0x1e31e  ldarg.0
0x1e31f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__15::<>7__wrap17
0x1e324  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1e329  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<item>5__16
0x1e32e  ldarg.0
0x1e32f  ldarg.0
0x1e330  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<item>5__16
0x1e335  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>2__current
0x1e33a  ldarg.0
0x1e33b  ldc.i4.2
0x1e33c  stfld    int32 <GetProperties>d__15::<>1__state
0x1e341  ldc.i4.1
0x1e342  stloc.0
0x1e343  leave    loc_1EA50
0x1e348  ldarg.0
0x1e349  ldc.i4.1
0x1e34a  stfld    int32 <GetProperties>d__15::<>1__state
0x1e34f  ldarg.0
0x1e350  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__15::<>7__wrap17
0x1e355  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1e35a  brtrue.s loc_1E31D
0x1e35c  ldarg.0
0x1e35d  call     instance void <GetProperties>d__15::<>m__Finally18()
0x1e362  ldarg.0
0x1e363  ldarg.0
0x1e364  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1e369  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e36e  ldarg.0
0x1e36f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e374  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x1e379  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1e37e  ldarg.0
0x1e37f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e384  ldc.i4.0
0x1e385  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1e38a  ldarg.0
0x1e38b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e390  ldc.i4.1
0x1e391  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1e396  ldarg.0
0x1e397  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e39c  ldc.i4.0
0x1e39d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1e3a2  ldarg.0
0x1e3a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e3a8  ldtoken  [mscorlib]System.Boolean
0x1e3ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e3b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1e3b7  ldarg.0
0x1e3b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e3bd  ldc.i4.0
0x1e3be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1e3c3  ldarg.0
0x1e3c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e3c9  ldc.i4.1
0x1e3ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1e3cf  ldarg.0
0x1e3d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e3d5  ldc.i4.0
0x1e3d6  box      [mscorlib]System.Boolean
0x1e3db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1e3e0  ldarg.0
0x1e3e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e3e6  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x1e3eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1e3f0  ldarg.0
0x1e3f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e3f6  ldnull
0x1e3f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1e3fc  ldarg.0
0x1e3fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e402  ldc.i4.0
0x1e403  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1e408  ldarg.0
0x1e409  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e40e  ldc.i4.0
0x1e40f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1e414  ldarg.0
0x1e415  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e41a  ldc.i4.0
0x1e41b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1e420  ldarg.0
0x1e421  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocald
0x1e426  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>2__current
0x1e42b  ldarg.0
0x1e42c  ldc.i4.3
0x1e42d  stfld    int32 <GetProperties>d__15::<>1__state
0x1e432  ldc.i4.1
0x1e433  stloc.0
0x1e434  leave    loc_1EA50
0x1e439  ldarg.0
0x1e43a  ldc.i4.m1
0x1e43b  stfld    int32 <GetProperties>d__15::<>1__state
0x1e440  ldarg.0
0x1e441  ldarg.0
0x1e442  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1e447  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e44c  ldarg.0
0x1e44d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e452  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x1e457  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1e45c  ldarg.0
0x1e45d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e462  ldc.i4.0
0x1e463  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1e468  ldarg.0
0x1e469  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e46e  ldc.i4.1
0x1e46f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1e474  ldarg.0
0x1e475  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e47a  ldc.i4.0
0x1e47b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1e480  ldarg.0
0x1e481  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e486  ldtoken  [mscorlib]System.Boolean
0x1e48b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e490  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1e495  ldarg.0
0x1e496  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e49b  ldc.i4.0
0x1e49c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1e4a1  ldarg.0
0x1e4a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e4a7  ldc.i4.1
0x1e4a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1e4ad  ldarg.0
0x1e4ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e4b3  ldc.i4.0
0x1e4b4  box      [mscorlib]System.Boolean
0x1e4b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1e4be  ldarg.0
0x1e4bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e4c4  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x1e4c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1e4ce  ldarg.0
0x1e4cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e4d4  ldnull
0x1e4d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1e4da  ldarg.0
0x1e4db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e4e0  ldc.i4.0
0x1e4e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1e4e6  ldarg.0
0x1e4e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e4ec  ldc.i4.0
0x1e4ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1e4f2  ldarg.0
0x1e4f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e4f8  ldc.i4.0
0x1e4f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1e4fe  ldarg.0
0x1e4ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocale
0x1e504  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>2__current
0x1e509  ldarg.0
0x1e50a  ldc.i4.4
0x1e50b  stfld    int32 <GetProperties>d__15::<>1__state
0x1e510  ldc.i4.1
0x1e511  stloc.0
0x1e512  leave    loc_1EA50
0x1e517  ldarg.0
0x1e518  ldc.i4.m1
0x1e519  stfld    int32 <GetProperties>d__15::<>1__state
0x1e51e  ldarg.0
0x1e51f  ldarg.0
0x1e520  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1e525  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e52a  ldarg.0
0x1e52b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e530  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x1e535  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1e53a  ldarg.0
0x1e53b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e540  ldc.i4.0
0x1e541  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1e546  ldarg.0
0x1e547  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e54c  ldc.i4.1
0x1e54d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1e552  ldarg.0
0x1e553  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e558  ldc.i4.0
0x1e559  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1e55e  ldarg.0
0x1e55f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e564  ldtoken  [mscorlib]System.Boolean
0x1e569  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e56e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1e573  ldarg.0
0x1e574  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e579  ldc.i4.0
0x1e57a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1e57f  ldarg.0
0x1e580  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e585  ldc.i4.1
0x1e586  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1e58b  ldarg.0
0x1e58c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e591  ldc.i4.0
0x1e592  box      [mscorlib]System.Boolean
0x1e597  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1e59c  ldarg.0
0x1e59d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e5a2  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x1e5a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1e5ac  ldarg.0
0x1e5ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e5b2  ldnull
0x1e5b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1e5b8  ldarg.0
0x1e5b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e5be  ldc.i4.0
0x1e5bf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1e5c4  ldarg.0
0x1e5c5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e5ca  ldc.i4.0
0x1e5cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1e5d0  ldarg.0
0x1e5d1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e5d6  ldc.i4.0
0x1e5d7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1e5dc  ldarg.0
0x1e5dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocalf
0x1e5e2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>2__current
0x1e5e7  ldarg.0
0x1e5e8  ldc.i4.5
0x1e5e9  stfld    int32 <GetProperties>d__15::<>1__state
0x1e5ee  ldc.i4.1
0x1e5ef  stloc.0
0x1e5f0  leave    loc_1EA50
0x1e5f5  ldarg.0
0x1e5f6  ldc.i4.m1
0x1e5f7  stfld    int32 <GetProperties>d__15::<>1__state
0x1e5fc  ldarg.0
0x1e5fd  ldarg.0
0x1e5fe  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1e603  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e608  ldarg.0
0x1e609  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e60e  ldstr    aServerrelative// "ServerRelativeSiteUrl"
0x1e613  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1e618  ldarg.0
0x1e619  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e61e  ldc.i4.0
0x1e61f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1e624  ldarg.0
0x1e625  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e62a  ldc.i4.1
0x1e62b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1e630  ldarg.0
0x1e631  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e636  ldc.i4.0
0x1e637  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1e63c  ldarg.0
0x1e63d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e642  ldtoken  [mscorlib]System.String
0x1e647  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e64c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1e651  ldarg.0
0x1e652  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e657  ldc.i4.1
0x1e658  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1e65d  ldarg.0
0x1e65e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e663  ldc.i4.1
0x1e664  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1e669  ldarg.0
0x1e66a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
0x1e66f  ldnull
0x1e670  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1e675  ldarg.0
0x1e676  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__15::<>g__initLocal10
  ... truncated ...
```
