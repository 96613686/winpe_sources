# <GetProperties>d__6::MoveNext_0

- ea: `0x2ba50`
- end: `0x2c02f`
- name: `<GetProperties>d__6::MoveNext_0`
- size: `1503`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x132e0`
- `0x2ba50`
- `0x2c050`
- `0x2c0b0`

## pseudocode

```c

```

## disassembly

```asm
0x2ba50  ldarg.0
0x2ba51  ldfld    int32 <GetProperties>d__6::<>1__state
0x2ba56  stloc.1
0x2ba57  ldloc.1
0x2ba58  switch   loc_2BA86, loc_2C022, loc_2BAF0, loc_2BBDC, loc_2BCBA, loc_2BD93, loc_2BE6C, loc_2BF45, loc_2C01B
0x2ba81  br       loc_2C022
0x2ba86  ldarg.0
0x2ba87  ldc.i4.m1
0x2ba88  stfld    int32 <GetProperties>d__6::<>1__state
0x2ba8d  ldarg.0
0x2ba8e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0x2ba93  brtrue.s loc_2BAA0
0x2ba95  ldstr    aProxycontext// "proxyContext"
0x2ba9a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2ba9f  throw
0x2baa0  ldarg.0
0x2baa1  ldarg.0
0x2baa2  ldfld    class Microsoft.SharePoint.Publishing.VariationLabelServerStub <GetProperties>d__6::<>4__this
0x2baa7  ldarg.0
0x2baa8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0x2baad  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.VariationLabelServerStub::<>n__FabricatedMethoda(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x2bab2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x2bab7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x2babc  ldarg.0
0x2babd  ldc.i4.1
0x2babe  stfld    int32 <GetProperties>d__6::<>1__state
0x2bac3  br.s     loc_2BAF7
0x2bac5  ldarg.0
0x2bac6  ldarg.0
0x2bac7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x2bacc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x2bad1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0x2bad6  ldarg.0
0x2bad7  ldarg.0
0x2bad8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0x2badd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x2bae2  ldarg.0
0x2bae3  ldc.i4.2
0x2bae4  stfld    int32 <GetProperties>d__6::<>1__state
0x2bae9  ldc.i4.1
0x2baea  stloc.0
0x2baeb  leave    loc_2C02D
0x2baf0  ldarg.0
0x2baf1  ldc.i4.1
0x2baf2  stfld    int32 <GetProperties>d__6::<>1__state
0x2baf7  ldarg.0
0x2baf8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x2bafd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2bb02  brtrue.s loc_2BAC5
0x2bb04  ldarg.0
0x2bb05  call     instance void <GetProperties>d__6::<>m__Finally9()
0x2bb0a  ldarg.0
0x2bb0b  ldarg.0
0x2bb0c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2bb11  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb16  ldarg.0
0x2bb17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb1c  ldstr    aDisplayname// "DisplayName"
0x2bb21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2bb26  ldarg.0
0x2bb27  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb2c  ldc.i4.0
0x2bb2d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2bb32  ldarg.0
0x2bb33  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb38  ldc.i4.1
0x2bb39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2bb3e  ldarg.0
0x2bb3f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb44  ldc.i4.0
0x2bb45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2bb4a  ldarg.0
0x2bb4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb50  ldtoken  [mscorlib]System.String
0x2bb55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bb5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2bb5f  ldarg.0
0x2bb60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb65  ldc.i4.1
0x2bb66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2bb6b  ldarg.0
0x2bb6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb71  ldc.i4.1
0x2bb72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2bb77  ldarg.0
0x2bb78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb7d  ldnull
0x2bb7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2bb83  ldarg.0
0x2bb84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb89  ldstr    aDisplayname// "DisplayName"
0x2bb8e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2bb93  ldarg.0
0x2bb94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bb99  ldnull
0x2bb9a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2bb9f  ldarg.0
0x2bba0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bba5  ldc.i4.1
0x2bba6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2bbab  ldarg.0
0x2bbac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bbb1  ldc.i4.0
0x2bbb2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2bbb7  ldarg.0
0x2bbb8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bbbd  ldc.i4.0
0x2bbbe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2bbc3  ldarg.0
0x2bbc4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2bbc9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x2bbce  ldarg.0
0x2bbcf  ldc.i4.3
0x2bbd0  stfld    int32 <GetProperties>d__6::<>1__state
0x2bbd5  ldc.i4.1
0x2bbd6  stloc.0
0x2bbd7  leave    loc_2C02D
0x2bbdc  ldarg.0
0x2bbdd  ldc.i4.m1
0x2bbde  stfld    int32 <GetProperties>d__6::<>1__state
0x2bbe3  ldarg.0
0x2bbe4  ldarg.0
0x2bbe5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2bbea  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bbef  ldarg.0
0x2bbf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bbf5  ldstr    aIssource// "IsSource"
0x2bbfa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2bbff  ldarg.0
0x2bc00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc05  ldc.i4.0
0x2bc06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2bc0b  ldarg.0
0x2bc0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc11  ldc.i4.1
0x2bc12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2bc17  ldarg.0
0x2bc18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc1d  ldc.i4.0
0x2bc1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2bc23  ldarg.0
0x2bc24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc29  ldtoken  [mscorlib]System.Boolean
0x2bc2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bc33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2bc38  ldarg.0
0x2bc39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc3e  ldc.i4.1
0x2bc3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2bc44  ldarg.0
0x2bc45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc4a  ldc.i4.1
0x2bc4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2bc50  ldarg.0
0x2bc51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc56  ldc.i4.0
0x2bc57  box      [mscorlib]System.Boolean
0x2bc5c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2bc61  ldarg.0
0x2bc62  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc67  ldstr    aIssource// "IsSource"
0x2bc6c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2bc71  ldarg.0
0x2bc72  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc77  ldnull
0x2bc78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2bc7d  ldarg.0
0x2bc7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc83  ldc.i4.1
0x2bc84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2bc89  ldarg.0
0x2bc8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc8f  ldc.i4.0
0x2bc90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2bc95  ldarg.0
0x2bc96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bc9b  ldc.i4.0
0x2bc9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2bca1  ldarg.0
0x2bca2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2bca7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x2bcac  ldarg.0
0x2bcad  ldc.i4.4
0x2bcae  stfld    int32 <GetProperties>d__6::<>1__state
0x2bcb3  ldc.i4.1
0x2bcb4  stloc.0
0x2bcb5  leave    loc_2C02D
0x2bcba  ldarg.0
0x2bcbb  ldc.i4.m1
0x2bcbc  stfld    int32 <GetProperties>d__6::<>1__state
0x2bcc1  ldarg.0
0x2bcc2  ldarg.0
0x2bcc3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2bcc8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bccd  ldarg.0
0x2bcce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bcd3  ldstr    aLanguage// "Language"
0x2bcd8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2bcdd  ldarg.0
0x2bcde  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bce3  ldc.i4.0
0x2bce4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2bce9  ldarg.0
0x2bcea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bcef  ldc.i4.1
0x2bcf0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2bcf5  ldarg.0
0x2bcf6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bcfb  ldc.i4.0
0x2bcfc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2bd01  ldarg.0
0x2bd02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd07  ldtoken  [mscorlib]System.String
0x2bd0c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bd11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2bd16  ldarg.0
0x2bd17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd1c  ldc.i4.1
0x2bd1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2bd22  ldarg.0
0x2bd23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd28  ldc.i4.1
0x2bd29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2bd2e  ldarg.0
0x2bd2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd34  ldnull
0x2bd35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2bd3a  ldarg.0
0x2bd3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd40  ldstr    aLanguage// "Language"
0x2bd45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2bd4a  ldarg.0
0x2bd4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd50  ldnull
0x2bd51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2bd56  ldarg.0
0x2bd57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd5c  ldc.i4.1
0x2bd5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2bd62  ldarg.0
0x2bd63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd68  ldc.i4.0
0x2bd69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2bd6e  ldarg.0
0x2bd6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd74  ldc.i4.0
0x2bd75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2bd7a  ldarg.0
0x2bd7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2bd80  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x2bd85  ldarg.0
0x2bd86  ldc.i4.5
0x2bd87  stfld    int32 <GetProperties>d__6::<>1__state
0x2bd8c  ldc.i4.1
0x2bd8d  stloc.0
0x2bd8e  leave    loc_2C02D
0x2bd93  ldarg.0
0x2bd94  ldc.i4.m1
0x2bd95  stfld    int32 <GetProperties>d__6::<>1__state
0x2bd9a  ldarg.0
0x2bd9b  ldarg.0
0x2bd9c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2bda1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2bda6  ldarg.0
0x2bda7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2bdac  ldstr    aLocale// "Locale"
0x2bdb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2bdb6  ldarg.0
0x2bdb7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2bdbc  ldc.i4.0
0x2bdbd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2bdc2  ldarg.0
0x2bdc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2bdc8  ldc.i4.1
0x2bdc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2bdce  ldarg.0
0x2bdcf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2bdd4  ldc.i4.0
0x2bdd5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2bdda  ldarg.0
0x2bddb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2bde0  ldtoken  [mscorlib]System.String
0x2bde5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bdea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2bdef  ldarg.0
0x2bdf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2bdf5  ldc.i4.1
0x2bdf6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2bdfb  ldarg.0
0x2bdfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2be01  ldc.i4.1
0x2be02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2be07  ldarg.0
0x2be08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2be0d  ldnull
0x2be0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2be13  ldarg.0
0x2be14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x2be19  ldstr    aLocale// "Locale"
0x2be1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
