# <GetProperties>d__4c::MoveNext

- ea: `0x1bba0`
- end: `0x1c961`
- name: `<GetProperties>d__4c::MoveNext`
- size: `3521`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x78d0`
- `0x1bba0`
- `0x1c990`
- `0x1c9f0`

## string_xrefs

- `0x1c6db`: `SimpleLinkUrl`
- `0x1c748`: `SimpleLinkUrl`

## pseudocode

```c

```

## disassembly

```asm
0x1bba0  ldarg.0
0x1bba1  ldfld    int32 <GetProperties>d__4c::<>1__state
0x1bba6  stloc.1
0x1bba7  ldloc.1
0x1bba8  switch   loc_1BBFA, loc_1C954, loc_1BC64, loc_1BD50, loc_1BE29, loc_1BF02, loc_1BFDB, loc_1C0B9, loc_1C197, loc_1C271, loc_1C34B, loc_1C42A, loc_1C509, loc_1C5E8, loc_1C6C2, loc_1C79C, loc_1C876, loc_1C94D
0x1bbf5  br       loc_1C954
0x1bbfa  ldarg.0
0x1bbfb  ldc.i4.m1
0x1bbfc  stfld    int32 <GetProperties>d__4c::<>1__state
0x1bc01  ldarg.0
0x1bc02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4c::proxyContext
0x1bc07  brtrue.s loc_1BC14
0x1bc09  ldstr    aProxycontext// "proxyContext"
0x1bc0e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1bc13  throw
0x1bc14  ldarg.0
0x1bc15  ldarg.0
0x1bc16  ldfld    class Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub <GetProperties>d__4c::<>4__this
0x1bc1b  ldarg.0
0x1bc1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4c::proxyContext
0x1bc21  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::<>n__FabricatedMethod50(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1bc26  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1bc2b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4c::<>7__wrap4e
0x1bc30  ldarg.0
0x1bc31  ldc.i4.1
0x1bc32  stfld    int32 <GetProperties>d__4c::<>1__state
0x1bc37  br.s     loc_1BC6B
0x1bc39  ldarg.0
0x1bc3a  ldarg.0
0x1bc3b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4c::<>7__wrap4e
0x1bc40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1bc45  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<item>5__4d
0x1bc4a  ldarg.0
0x1bc4b  ldarg.0
0x1bc4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<item>5__4d
0x1bc51  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>2__current
0x1bc56  ldarg.0
0x1bc57  ldc.i4.2
0x1bc58  stfld    int32 <GetProperties>d__4c::<>1__state
0x1bc5d  ldc.i4.1
0x1bc5e  stloc.0
0x1bc5f  leave    loc_1C95F
0x1bc64  ldarg.0
0x1bc65  ldc.i4.1
0x1bc66  stfld    int32 <GetProperties>d__4c::<>1__state
0x1bc6b  ldarg.0
0x1bc6c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4c::<>7__wrap4e
0x1bc71  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bc76  brtrue.s loc_1BC39
0x1bc78  ldarg.0
0x1bc79  call     instance void <GetProperties>d__4c::<>m__Finally4f()
0x1bc7e  ldarg.0
0x1bc7f  ldarg.0
0x1bc80  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1bc85  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bc8a  ldarg.0
0x1bc8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bc90  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x1bc95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1bc9a  ldarg.0
0x1bc9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bca0  ldc.i4.0
0x1bca1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1bca6  ldarg.0
0x1bca7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bcac  ldc.i4.1
0x1bcad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1bcb2  ldarg.0
0x1bcb3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bcb8  ldc.i4.0
0x1bcb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1bcbe  ldarg.0
0x1bcbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bcc4  ldtoken  [mscorlib]System.String
0x1bcc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1bcd3  ldarg.0
0x1bcd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bcd9  ldc.i4.0
0x1bcda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1bcdf  ldarg.0
0x1bce0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bce5  ldc.i4.1
0x1bce6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1bceb  ldarg.0
0x1bcec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bcf1  ldnull
0x1bcf2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1bcf7  ldarg.0
0x1bcf8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bcfd  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x1bd02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1bd07  ldarg.0
0x1bd08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bd0d  ldnull
0x1bd0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1bd13  ldarg.0
0x1bd14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bd19  ldc.i4.0
0x1bd1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1bd1f  ldarg.0
0x1bd20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bd25  ldc.i4.0
0x1bd26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1bd2b  ldarg.0
0x1bd2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bd31  ldc.i4.0
0x1bd32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1bd37  ldarg.0
0x1bd38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3d
0x1bd3d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>2__current
0x1bd42  ldarg.0
0x1bd43  ldc.i4.3
0x1bd44  stfld    int32 <GetProperties>d__4c::<>1__state
0x1bd49  ldc.i4.1
0x1bd4a  stloc.0
0x1bd4b  leave    loc_1C95F
0x1bd50  ldarg.0
0x1bd51  ldc.i4.m1
0x1bd52  stfld    int32 <GetProperties>d__4c::<>1__state
0x1bd57  ldarg.0
0x1bd58  ldarg.0
0x1bd59  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1bd5e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bd63  ldarg.0
0x1bd64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bd69  ldstr    aCatalogtargetu_0// "CatalogTargetUrl"
0x1bd6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1bd73  ldarg.0
0x1bd74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bd79  ldc.i4.0
0x1bd7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1bd7f  ldarg.0
0x1bd80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bd85  ldc.i4.4
0x1bd86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1bd8b  ldarg.0
0x1bd8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bd91  ldc.i4.0
0x1bd92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1bd97  ldarg.0
0x1bd98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bd9d  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString
0x1bda2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bda7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1bdac  ldarg.0
0x1bdad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bdb2  ldc.i4.1
0x1bdb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1bdb8  ldarg.0
0x1bdb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bdbe  ldc.i4.1
0x1bdbf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1bdc4  ldarg.0
0x1bdc5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bdca  ldnull
0x1bdcb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1bdd0  ldarg.0
0x1bdd1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bdd6  ldstr    aCatalogtargetu_0// "CatalogTargetUrl"
0x1bddb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1bde0  ldarg.0
0x1bde1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bde6  ldnull
0x1bde7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1bdec  ldarg.0
0x1bded  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bdf2  ldc.i4.0
0x1bdf3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1bdf8  ldarg.0
0x1bdf9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1bdfe  ldc.i4.0
0x1bdff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1be04  ldarg.0
0x1be05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1be0a  ldc.i4.0
0x1be0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1be10  ldarg.0
0x1be11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3e
0x1be16  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>2__current
0x1be1b  ldarg.0
0x1be1c  ldc.i4.4
0x1be1d  stfld    int32 <GetProperties>d__4c::<>1__state
0x1be22  ldc.i4.1
0x1be23  stloc.0
0x1be24  leave    loc_1C95F
0x1be29  ldarg.0
0x1be2a  ldc.i4.m1
0x1be2b  stfld    int32 <GetProperties>d__4c::<>1__state
0x1be30  ldarg.0
0x1be31  ldarg.0
0x1be32  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1be37  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be3c  ldarg.0
0x1be3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be42  ldstr    aCategoryimageu// "CategoryImageUrl"
0x1be47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1be4c  ldarg.0
0x1be4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be52  ldc.i4.0
0x1be53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1be58  ldarg.0
0x1be59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be5e  ldc.i4.1
0x1be5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1be64  ldarg.0
0x1be65  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be6a  ldc.i4.0
0x1be6b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1be70  ldarg.0
0x1be71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be76  ldtoken  [mscorlib]System.String
0x1be7b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1be80  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1be85  ldarg.0
0x1be86  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be8b  ldc.i4.0
0x1be8c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1be91  ldarg.0
0x1be92  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1be97  ldc.i4.1
0x1be98  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1be9d  ldarg.0
0x1be9e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1bea3  ldnull
0x1bea4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1bea9  ldarg.0
0x1beaa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1beaf  ldstr    aCategoryimageu// "CategoryImageUrl"
0x1beb4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1beb9  ldarg.0
0x1beba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1bebf  ldnull
0x1bec0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1bec5  ldarg.0
0x1bec6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1becb  ldc.i4.0
0x1becc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1bed1  ldarg.0
0x1bed2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1bed7  ldc.i4.0
0x1bed8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1bedd  ldarg.0
0x1bede  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1bee3  ldc.i4.0
0x1bee4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1bee9  ldarg.0
0x1beea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal3f
0x1beef  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>2__current
0x1bef4  ldarg.0
0x1bef5  ldc.i4.5
0x1bef6  stfld    int32 <GetProperties>d__4c::<>1__state
0x1befb  ldc.i4.1
0x1befc  stloc.0
0x1befd  leave    loc_1C95F
0x1bf02  ldarg.0
0x1bf03  ldc.i4.m1
0x1bf04  stfld    int32 <GetProperties>d__4c::<>1__state
0x1bf09  ldarg.0
0x1bf0a  ldarg.0
0x1bf0b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1bf10  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf15  ldarg.0
0x1bf16  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf1b  ldstr    aExcludedprovid// "ExcludedProviders"
0x1bf20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1bf25  ldarg.0
0x1bf26  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf2b  ldc.i4.0
0x1bf2c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1bf31  ldarg.0
0x1bf32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf37  ldc.i4.4
0x1bf38  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1bf3d  ldarg.0
0x1bf3e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf43  ldc.i4.0
0x1bf44  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1bf49  ldarg.0
0x1bf4a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf4f  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom
0x1bf54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bf59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1bf5e  ldarg.0
0x1bf5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf64  ldc.i4.1
0x1bf65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1bf6a  ldarg.0
0x1bf6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf70  ldc.i4.1
0x1bf71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1bf76  ldarg.0
0x1bf77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf7c  ldnull
0x1bf7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1bf82  ldarg.0
0x1bf83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4c::<>g__initLocal40
0x1bf88  ldstr    aExcludedprovid_0// "ExcludedProvidersCsom"
0x1bf8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1bf92  ldarg.0
  ... truncated ...
```
