# <GetProperties>d__12::MoveNext

- ea: `0x17750`
- end: `0x187a1`
- name: `<GetProperties>d__12::MoveNext`
- size: `4177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x4910`
- `0x17750`
- `0x187d0`
- `0x18830`

## string_xrefs

- `0x17bb5`: `EmbedServiceResponseCode`
- `0x17c27`: `EmbedServiceResponseCode`

## pseudocode

```c

```

## disassembly

```asm
0x17750  ldarg.0
0x17751  ldfld    int32 <GetProperties>d__12::<>1__state
0x17756  stloc.1
0x17757  ldloc.1
0x17758  switch   loc_177B6, loc_18794, loc_17820, loc_17911, loc_179EA, loc_17AC3, loc_17B9C, loc_17C7A, loc_17D53, loc_17E2D, loc_17F07, loc_17FE1, loc_180C0, loc_1819A, loc_18274, loc_1834E, loc_18428, loc_18502, loc_185DC, loc_186B6, loc_1878D
0x177b1  br       loc_18794
0x177b6  ldarg.0
0x177b7  ldc.i4.m1
0x177b8  stfld    int32 <GetProperties>d__12::<>1__state
0x177bd  ldarg.0
0x177be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__12::proxyContext
0x177c3  brtrue.s loc_177D0
0x177c5  ldstr    aProxycontext// "proxyContext"
0x177ca  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x177cf  throw
0x177d0  ldarg.0
0x177d1  ldarg.0
0x177d2  ldfld    class Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub <GetProperties>d__12::<>4__this
0x177d7  ldarg.0
0x177d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__12::proxyContext
0x177dd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::<>n__FabricatedMethod16(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x177e2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x177e7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__12::<>7__wrap14
0x177ec  ldarg.0
0x177ed  ldc.i4.1
0x177ee  stfld    int32 <GetProperties>d__12::<>1__state
0x177f3  br.s     loc_17827
0x177f5  ldarg.0
0x177f6  ldarg.0
0x177f7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__12::<>7__wrap14
0x177fc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x17801  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<item>5__13
0x17806  ldarg.0
0x17807  ldarg.0
0x17808  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<item>5__13
0x1780d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0x17812  ldarg.0
0x17813  ldc.i4.2
0x17814  stfld    int32 <GetProperties>d__12::<>1__state
0x17819  ldc.i4.1
0x1781a  stloc.0
0x1781b  leave    loc_1879F
0x17820  ldarg.0
0x17821  ldc.i4.1
0x17822  stfld    int32 <GetProperties>d__12::<>1__state
0x17827  ldarg.0
0x17828  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__12::<>7__wrap14
0x1782d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17832  brtrue.s loc_177F5
0x17834  ldarg.0
0x17835  call     instance void <GetProperties>d__12::<>m__Finally15()
0x1783a  ldarg.0
0x1783b  ldarg.0
0x1783c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x17841  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x17846  ldarg.0
0x17847  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x1784c  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x17851  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17856  ldarg.0
0x17857  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x1785c  ldc.i4.0
0x1785d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17862  ldarg.0
0x17863  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x17868  ldc.i4.1
0x17869  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1786e  ldarg.0
0x1786f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x17874  ldc.i4.0
0x17875  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1787a  ldarg.0
0x1787b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x17880  ldtoken  [mscorlib]System.Boolean
0x17885  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1788a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1788f  ldarg.0
0x17890  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x17895  ldc.i4.0
0x17896  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1789b  ldarg.0
0x1789c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178a1  ldc.i4.1
0x178a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x178a7  ldarg.0
0x178a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178ad  ldc.i4.0
0x178ae  box      [mscorlib]System.Boolean
0x178b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x178b8  ldarg.0
0x178b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178be  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x178c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x178c8  ldarg.0
0x178c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178ce  ldnull
0x178cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x178d4  ldarg.0
0x178d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178da  ldc.i4.0
0x178db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x178e0  ldarg.0
0x178e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178e6  ldc.i4.0
0x178e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x178ec  ldarg.0
0x178ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178f2  ldc.i4.0
0x178f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x178f8  ldarg.0
0x178f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0x178fe  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0x17903  ldarg.0
0x17904  ldc.i4.3
0x17905  stfld    int32 <GetProperties>d__12::<>1__state
0x1790a  ldc.i4.1
0x1790b  stloc.0
0x1790c  leave    loc_1879F
0x17911  ldarg.0
0x17912  ldc.i4.m1
0x17913  stfld    int32 <GetProperties>d__12::<>1__state
0x17918  ldarg.0
0x17919  ldarg.0
0x1791a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1791f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x17924  ldarg.0
0x17925  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x1792a  ldstr    aCreatorname// "CreatorName"
0x1792f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17934  ldarg.0
0x17935  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x1793a  ldc.i4.0
0x1793b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17940  ldarg.0
0x17941  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x17946  ldc.i4.1
0x17947  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1794c  ldarg.0
0x1794d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x17952  ldc.i4.0
0x17953  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17958  ldarg.0
0x17959  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x1795e  ldtoken  [mscorlib]System.String
0x17963  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17968  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1796d  ldarg.0
0x1796e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x17973  ldc.i4.0
0x17974  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17979  ldarg.0
0x1797a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x1797f  ldc.i4.1
0x17980  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x17985  ldarg.0
0x17986  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x1798b  ldnull
0x1798c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x17991  ldarg.0
0x17992  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x17997  ldstr    aCreatorname// "CreatorName"
0x1799c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x179a1  ldarg.0
0x179a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x179a7  ldnull
0x179a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x179ad  ldarg.0
0x179ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x179b3  ldc.i4.0
0x179b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x179b9  ldarg.0
0x179ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x179bf  ldc.i4.0
0x179c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x179c5  ldarg.0
0x179c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x179cb  ldc.i4.0
0x179cc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x179d1  ldarg.0
0x179d2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0x179d7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0x179dc  ldarg.0
0x179dd  ldc.i4.4
0x179de  stfld    int32 <GetProperties>d__12::<>1__state
0x179e3  ldc.i4.1
0x179e4  stloc.0
0x179e5  leave    loc_1879F
0x179ea  ldarg.0
0x179eb  ldc.i4.m1
0x179ec  stfld    int32 <GetProperties>d__12::<>1__state
0x179f1  ldarg.0
0x179f2  ldarg.0
0x179f3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x179f8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x179fd  ldarg.0
0x179fe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a03  ldstr    aDatepublisheda// "DatePublishedAt"
0x17a08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17a0d  ldarg.0
0x17a0e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a13  ldc.i4.0
0x17a14  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17a19  ldarg.0
0x17a1a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a1f  ldc.i4.1
0x17a20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17a25  ldarg.0
0x17a26  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a2b  ldc.i4.0
0x17a2c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17a31  ldarg.0
0x17a32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a37  ldtoken  [mscorlib]System.String
0x17a3c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17a41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x17a46  ldarg.0
0x17a47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a4c  ldc.i4.0
0x17a4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17a52  ldarg.0
0x17a53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a58  ldc.i4.1
0x17a59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x17a5e  ldarg.0
0x17a5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a64  ldnull
0x17a65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x17a6a  ldarg.0
0x17a6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a70  ldstr    aDatepublisheda// "DatePublishedAt"
0x17a75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x17a7a  ldarg.0
0x17a7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a80  ldnull
0x17a81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x17a86  ldarg.0
0x17a87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a8c  ldc.i4.0
0x17a8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x17a92  ldarg.0
0x17a93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17a98  ldc.i4.0
0x17a99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x17a9e  ldarg.0
0x17a9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17aa4  ldc.i4.0
0x17aa5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x17aaa  ldarg.0
0x17aab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0x17ab0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0x17ab5  ldarg.0
0x17ab6  ldc.i4.5
0x17ab7  stfld    int32 <GetProperties>d__12::<>1__state
0x17abc  ldc.i4.1
0x17abd  stloc.0
0x17abe  leave    loc_1879F
0x17ac3  ldarg.0
0x17ac4  ldc.i4.m1
0x17ac5  stfld    int32 <GetProperties>d__12::<>1__state
0x17aca  ldarg.0
0x17acb  ldarg.0
0x17acc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x17ad1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17ad6  ldarg.0
0x17ad7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17adc  ldstr    aDescription// "Description"
0x17ae1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17ae6  ldarg.0
0x17ae7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17aec  ldc.i4.0
0x17aed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17af2  ldarg.0
0x17af3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17af8  ldc.i4.1
0x17af9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17afe  ldarg.0
0x17aff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17b04  ldc.i4.0
0x17b05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17b0a  ldarg.0
0x17b0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17b10  ldtoken  [mscorlib]System.String
0x17b15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17b1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x17b1f  ldarg.0
0x17b20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17b25  ldc.i4.0
0x17b26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17b2b  ldarg.0
0x17b2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17b31  ldc.i4.1
0x17b32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x17b37  ldarg.0
0x17b38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17b3d  ldnull
0x17b3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x17b43  ldarg.0
0x17b44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0x17b49  ldstr    aDescription// "Description"
0x17b4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
