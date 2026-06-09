# <GetProperties>d__1d::MoveNext_0

- ea: `0x1a5ea0`
- end: `0x1a78c8`
- name: `<GetProperties>d__1d::MoveNext_0`
- size: `6696`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xacc40`
- `0x1a5ea0`
- `0x1a78f0`
- `0x1a7950`

## string_xrefs

- `0x1a66a4`: `LinkingUrl`
- `0x1a6711`: `LinkingUrl`
- `0x1a6339`: `Extension`
- `0x1a63a6`: `Extension`
- `0x1a7634`: `UrlPath`
- `0x1a76a1`: `UrlPath`
- `0x1a770e`: `VideoManifestUrl`
- `0x1a777b`: `VideoManifestUrl`

## pseudocode

```c

```

## disassembly

```asm
0x1a5ea0  ldarg.0
0x1a5ea1  ldfld    int32 <GetProperties>d__1d::<>1__state
0x1a5ea6  stloc.1
0x1a5ea7  ldloc.1
0x1a5ea8  switch   loc_1A5F32, loc_1A78BB, loc_1A5F9C, loc_1A6088, loc_1A6161, loc_1A6247, loc_1A6320, loc_1A63F9, loc_1A64D2, loc_1A65AC, loc_1A668B, loc_1A6765, loc_1A684C, loc_1A692B, loc_1A6A05, loc_1A6AED, loc_1A6BC7, loc_1A6CA1, loc_1A6D7B, loc_1A6E55, loc_1A6F2F, loc_1A7009, loc_1A70E3, loc_1A71CB, loc_1A72A5, loc_1A737F, loc_1A7459, loc_1A7533, loc_1A761B, loc_1A76F5, loc_1A77CF, loc_1A78B4
0x1a5f2d  br       loc_1A78BB
0x1a5f32  ldarg.0
0x1a5f33  ldc.i4.m1
0x1a5f34  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a5f39  ldarg.0
0x1a5f3a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1d::proxyContext
0x1a5f3f  brtrue.s loc_1A5F4C
0x1a5f41  ldstr    aProxycontext// "proxyContext"
0x1a5f46  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a5f4b  throw
0x1a5f4c  ldarg.0
0x1a5f4d  ldarg.0
0x1a5f4e  ldfld    class Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub <GetProperties>d__1d::<>4__this
0x1a5f53  ldarg.0
0x1a5f54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1d::proxyContext
0x1a5f59  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::<>n__FabricatedMethod21(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1a5f5e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1a5f63  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x1a5f68  ldarg.0
0x1a5f69  ldc.i4.1
0x1a5f6a  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a5f6f  br.s     loc_1A5FA3
0x1a5f71  ldarg.0
0x1a5f72  ldarg.0
0x1a5f73  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x1a5f78  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1a5f7d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<item>5__1e
0x1a5f82  ldarg.0
0x1a5f83  ldarg.0
0x1a5f84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<item>5__1e
0x1a5f89  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1a5f8e  ldarg.0
0x1a5f8f  ldc.i4.2
0x1a5f90  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a5f95  ldc.i4.1
0x1a5f96  stloc.0
0x1a5f97  leave    loc_1A78C6
0x1a5f9c  ldarg.0
0x1a5f9d  ldc.i4.1
0x1a5f9e  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a5fa3  ldarg.0
0x1a5fa4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x1a5fa9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a5fae  brtrue.s loc_1A5F71
0x1a5fb0  ldarg.0
0x1a5fb1  call     instance void <GetProperties>d__1d::<>m__Finally20()
0x1a5fb6  ldarg.0
0x1a5fb7  ldarg.0
0x1a5fb8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a5fbd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a5fc2  ldarg.0
0x1a5fc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a5fc8  ldstr    aAuthor_0// "Author"
0x1a5fcd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a5fd2  ldarg.0
0x1a5fd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a5fd8  ldc.i4.0
0x1a5fd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a5fde  ldarg.0
0x1a5fdf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a5fe4  ldc.i4.2
0x1a5fe5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a5fea  ldarg.0
0x1a5feb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a5ff0  ldc.i4.0
0x1a5ff1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a5ff6  ldarg.0
0x1a5ff7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a5ffc  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal
0x1a6001  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a6006  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a600b  ldarg.0
0x1a600c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a6011  ldc.i4.0
0x1a6012  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a6017  ldarg.0
0x1a6018  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a601d  ldc.i4.1
0x1a601e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a6023  ldarg.0
0x1a6024  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a6029  ldnull
0x1a602a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a602f  ldarg.0
0x1a6030  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a6035  ldstr    aAuthor_0// "Author"
0x1a603a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a603f  ldarg.0
0x1a6040  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a6045  ldnull
0x1a6046  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a604b  ldarg.0
0x1a604c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a6051  ldc.i4.0
0x1a6052  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a6057  ldarg.0
0x1a6058  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a605d  ldc.i4.0
0x1a605e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a6063  ldarg.0
0x1a6064  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a6069  ldc.i4.0
0x1a606a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a606f  ldarg.0
0x1a6070  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal0
0x1a6075  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1a607a  ldarg.0
0x1a607b  ldc.i4.3
0x1a607c  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a6081  ldc.i4.1
0x1a6082  stloc.0
0x1a6083  leave    loc_1A78C6
0x1a6088  ldarg.0
0x1a6089  ldc.i4.m1
0x1a608a  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a608f  ldarg.0
0x1a6090  ldarg.0
0x1a6091  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a6096  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a609b  ldarg.0
0x1a609c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a60a1  ldstr    aCallerstack// "CallerStack"
0x1a60a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a60ab  ldarg.0
0x1a60ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a60b1  ldc.i4.0
0x1a60b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a60b7  ldarg.0
0x1a60b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a60bd  ldc.i4.1
0x1a60be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a60c3  ldarg.0
0x1a60c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a60c9  ldc.i4.1
0x1a60ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a60cf  ldarg.0
0x1a60d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a60d5  ldtoken  [mscorlib]System.String
0x1a60da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a60df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a60e4  ldarg.0
0x1a60e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a60ea  ldc.i4.1
0x1a60eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a60f0  ldarg.0
0x1a60f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a60f6  ldc.i4.1
0x1a60f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a60fc  ldarg.0
0x1a60fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a6102  ldnull
0x1a6103  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a6108  ldarg.0
0x1a6109  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a610e  ldstr    aCallerstack// "CallerStack"
0x1a6113  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a6118  ldarg.0
0x1a6119  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a611e  ldnull
0x1a611f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a6124  ldarg.0
0x1a6125  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a612a  ldc.i4.0
0x1a612b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a6130  ldarg.0
0x1a6131  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a6136  ldc.i4.1
0x1a6137  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a613c  ldarg.0
0x1a613d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a6142  ldc.i4.0
0x1a6143  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a6148  ldarg.0
0x1a6149  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1
0x1a614e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1a6153  ldarg.0
0x1a6154  ldc.i4.4
0x1a6155  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a615a  ldc.i4.1
0x1a615b  stloc.0
0x1a615c  leave    loc_1A78C6
0x1a6161  ldarg.0
0x1a6162  ldc.i4.m1
0x1a6163  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a6168  ldarg.0
0x1a6169  ldarg.0
0x1a616a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a616f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a6174  ldarg.0
0x1a6175  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a617a  ldstr    aContenttypeid_0// "ContentTypeId"
0x1a617f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a6184  ldarg.0
0x1a6185  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a618a  ldc.i4.0
0x1a618b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a6190  ldarg.0
0x1a6191  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a6196  ldc.i4.2
0x1a6197  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a619c  ldarg.0
0x1a619d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a61a2  ldc.i4.0
0x1a61a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a61a8  ldarg.0
0x1a61a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a61ae  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0x1a61b3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a61b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a61bd  ldarg.0
0x1a61be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a61c3  ldc.i4.0
0x1a61c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a61c9  ldarg.0
0x1a61ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a61cf  ldc.i4.1
0x1a61d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a61d5  ldarg.0
0x1a61d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a61db  ldloca.s 2
0x1a61dd  initobj  [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0x1a61e3  ldloc.2
0x1a61e4  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0x1a61e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a61ee  ldarg.0
0x1a61ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a61f4  ldstr    aContenttypeid_0// "ContentTypeId"
0x1a61f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a61fe  ldarg.0
0x1a61ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a6204  ldnull
0x1a6205  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a620a  ldarg.0
0x1a620b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a6210  ldc.i4.0
0x1a6211  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a6216  ldarg.0
0x1a6217  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a621c  ldc.i4.0
0x1a621d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a6222  ldarg.0
0x1a6223  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a6228  ldc.i4.0
0x1a6229  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a622e  ldarg.0
0x1a622f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal2
0x1a6234  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1a6239  ldarg.0
0x1a623a  ldc.i4.5
0x1a623b  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a6240  ldc.i4.1
0x1a6241  stloc.0
0x1a6242  leave    loc_1A78C6
0x1a6247  ldarg.0
0x1a6248  ldc.i4.m1
0x1a6249  stfld    int32 <GetProperties>d__1d::<>1__state
0x1a624e  ldarg.0
0x1a624f  ldarg.0
0x1a6250  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a6255  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a625a  ldarg.0
0x1a625b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a6260  ldstr    aEditor// "Editor"
0x1a6265  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a626a  ldarg.0
0x1a626b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a6270  ldc.i4.0
0x1a6271  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a6276  ldarg.0
0x1a6277  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a627c  ldc.i4.2
0x1a627d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a6282  ldarg.0
0x1a6283  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a6288  ldc.i4.0
0x1a6289  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a628e  ldarg.0
0x1a628f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a6294  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal
0x1a6299  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a629e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a62a3  ldarg.0
0x1a62a4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a62a9  ldc.i4.0
0x1a62aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a62af  ldarg.0
0x1a62b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a62b5  ldc.i4.1
0x1a62b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a62bb  ldarg.0
0x1a62bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
0x1a62c1  ldnull
0x1a62c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a62c7  ldarg.0
0x1a62c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal3
  ... truncated ...
```
