# <GetProperties>d__9::MoveNext

- ea: `0x24cb0`
- end: `0x2552e`
- name: `<GetProperties>d__9::MoveNext`
- size: `2174`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xdec0`
- `0x24cb0`
- `0x25550`
- `0x255b0`

## string_xrefs

- `0x2545c`: `WebRelativeFolderPath`
- `0x254c9`: `WebRelativeFolderPath`

## pseudocode

```c

```

## disassembly

```asm
0x24cb0  ldarg.0
0x24cb1  ldfld    int32 <GetProperties>d__9::<>1__state
0x24cb6  stloc.1
0x24cb7  ldloc.1
0x24cb8  switch   loc_24CF2, loc_25521, loc_24D5C, loc_24E48, loc_24F21, loc_24FFA, loc_250D3, loc_251AC, loc_2528A, loc_25369, loc_25443, loc_2551A
0x24ced  br       loc_25521
0x24cf2  ldarg.0
0x24cf3  ldc.i4.m1
0x24cf4  stfld    int32 <GetProperties>d__9::<>1__state
0x24cf9  ldarg.0
0x24cfa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__9::proxyContext
0x24cff  brtrue.s loc_24D0C
0x24d01  ldstr    aProxycontext// "proxyContext"
0x24d06  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24d0b  throw
0x24d0c  ldarg.0
0x24d0d  ldarg.0
0x24d0e  ldfld    class Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter <GetProperties>d__9::<>4__this
0x24d13  ldarg.0
0x24d14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__9::proxyContext
0x24d19  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::<>n__FabricatedMethodd(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x24d1e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x24d23  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__9::<>7__wrapb
0x24d28  ldarg.0
0x24d29  ldc.i4.1
0x24d2a  stfld    int32 <GetProperties>d__9::<>1__state
0x24d2f  br.s     loc_24D63
0x24d31  ldarg.0
0x24d32  ldarg.0
0x24d33  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__9::<>7__wrapb
0x24d38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x24d3d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<item>5__a
0x24d42  ldarg.0
0x24d43  ldarg.0
0x24d44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<item>5__a
0x24d49  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x24d4e  ldarg.0
0x24d4f  ldc.i4.2
0x24d50  stfld    int32 <GetProperties>d__9::<>1__state
0x24d55  ldc.i4.1
0x24d56  stloc.0
0x24d57  leave    loc_2552C
0x24d5c  ldarg.0
0x24d5d  ldc.i4.1
0x24d5e  stfld    int32 <GetProperties>d__9::<>1__state
0x24d63  ldarg.0
0x24d64  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__9::<>7__wrapb
0x24d69  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24d6e  brtrue.s loc_24D31
0x24d70  ldarg.0
0x24d71  call     instance void <GetProperties>d__9::<>m__Finallyc()
0x24d76  ldarg.0
0x24d77  ldarg.0
0x24d78  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x24d7d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24d82  ldarg.0
0x24d83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24d88  ldstr    aCanvascontent1// "CanvasContent1"
0x24d8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x24d92  ldarg.0
0x24d93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24d98  ldc.i4.0
0x24d99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x24d9e  ldarg.0
0x24d9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24da4  ldc.i4.1
0x24da5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x24daa  ldarg.0
0x24dab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24db0  ldc.i4.0
0x24db1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x24db6  ldarg.0
0x24db7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24dbc  ldtoken  [mscorlib]System.String
0x24dc1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24dc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x24dcb  ldarg.0
0x24dcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24dd1  ldc.i4.0
0x24dd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x24dd7  ldarg.0
0x24dd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24ddd  ldc.i4.1
0x24dde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x24de3  ldarg.0
0x24de4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24de9  ldnull
0x24dea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x24def  ldarg.0
0x24df0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24df5  ldstr    aCanvascontent1// "CanvasContent1"
0x24dfa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x24dff  ldarg.0
0x24e00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24e05  ldnull
0x24e06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x24e0b  ldarg.0
0x24e0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24e11  ldc.i4.0
0x24e12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x24e17  ldarg.0
0x24e18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24e1d  ldc.i4.0
0x24e1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x24e23  ldarg.0
0x24e24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24e29  ldc.i4.0
0x24e2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x24e2f  ldarg.0
0x24e30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x24e35  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x24e3a  ldarg.0
0x24e3b  ldc.i4.3
0x24e3c  stfld    int32 <GetProperties>d__9::<>1__state
0x24e41  ldc.i4.1
0x24e42  stloc.0
0x24e43  leave    loc_2552C
0x24e48  ldarg.0
0x24e49  ldc.i4.m1
0x24e4a  stfld    int32 <GetProperties>d__9::<>1__state
0x24e4f  ldarg.0
0x24e50  ldarg.0
0x24e51  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x24e56  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24e5b  ldarg.0
0x24e5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24e61  ldstr    aContenttypeid// "ContentTypeId"
0x24e66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x24e6b  ldarg.0
0x24e6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24e71  ldc.i4.0
0x24e72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x24e77  ldarg.0
0x24e78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24e7d  ldc.i4.1
0x24e7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x24e83  ldarg.0
0x24e84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24e89  ldc.i4.0
0x24e8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x24e8f  ldarg.0
0x24e90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24e95  ldtoken  [mscorlib]System.String
0x24e9a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24e9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x24ea4  ldarg.0
0x24ea5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24eaa  ldc.i4.0
0x24eab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x24eb0  ldarg.0
0x24eb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24eb6  ldc.i4.1
0x24eb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x24ebc  ldarg.0
0x24ebd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24ec2  ldnull
0x24ec3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x24ec8  ldarg.0
0x24ec9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24ece  ldstr    aContenttypeid// "ContentTypeId"
0x24ed3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x24ed8  ldarg.0
0x24ed9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24ede  ldnull
0x24edf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x24ee4  ldarg.0
0x24ee5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24eea  ldc.i4.0
0x24eeb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x24ef0  ldarg.0
0x24ef1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24ef6  ldc.i4.0
0x24ef7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x24efc  ldarg.0
0x24efd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24f02  ldc.i4.0
0x24f03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x24f08  ldarg.0
0x24f09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x24f0e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x24f13  ldarg.0
0x24f14  ldc.i4.4
0x24f15  stfld    int32 <GetProperties>d__9::<>1__state
0x24f1a  ldc.i4.1
0x24f1b  stloc.0
0x24f1c  leave    loc_2552C
0x24f21  ldarg.0
0x24f22  ldc.i4.m1
0x24f23  stfld    int32 <GetProperties>d__9::<>1__state
0x24f28  ldarg.0
0x24f29  ldarg.0
0x24f2a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x24f2f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f34  ldarg.0
0x24f35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f3a  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x24f3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x24f44  ldarg.0
0x24f45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f4a  ldc.i4.0
0x24f4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x24f50  ldarg.0
0x24f51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f56  ldc.i4.1
0x24f57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x24f5c  ldarg.0
0x24f5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f62  ldc.i4.0
0x24f63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x24f68  ldarg.0
0x24f69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f6e  ldtoken  [mscorlib]System.String
0x24f73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24f78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x24f7d  ldarg.0
0x24f7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f83  ldc.i4.0
0x24f84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x24f89  ldarg.0
0x24f8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f8f  ldc.i4.1
0x24f90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x24f95  ldarg.0
0x24f96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24f9b  ldnull
0x24f9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x24fa1  ldarg.0
0x24fa2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24fa7  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x24fac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x24fb1  ldarg.0
0x24fb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24fb7  ldnull
0x24fb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x24fbd  ldarg.0
0x24fbe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24fc3  ldc.i4.0
0x24fc4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x24fc9  ldarg.0
0x24fca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24fcf  ldc.i4.0
0x24fd0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x24fd5  ldarg.0
0x24fd6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24fdb  ldc.i4.0
0x24fdc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x24fe1  ldarg.0
0x24fe2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x24fe7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x24fec  ldarg.0
0x24fed  ldc.i4.5
0x24fee  stfld    int32 <GetProperties>d__9::<>1__state
0x24ff3  ldc.i4.1
0x24ff4  stloc.0
0x24ff5  leave    loc_2552C
0x24ffa  ldarg.0
0x24ffb  ldc.i4.m1
0x24ffc  stfld    int32 <GetProperties>d__9::<>1__state
0x25001  ldarg.0
0x25002  ldarg.0
0x25003  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x25008  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x2500d  ldarg.0
0x2500e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x25013  ldstr    aName// "Name"
0x25018  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2501d  ldarg.0
0x2501e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x25023  ldc.i4.0
0x25024  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x25029  ldarg.0
0x2502a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x2502f  ldc.i4.1
0x25030  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x25035  ldarg.0
0x25036  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x2503b  ldc.i4.0
0x2503c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x25041  ldarg.0
0x25042  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x25047  ldtoken  [mscorlib]System.String
0x2504c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25051  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x25056  ldarg.0
0x25057  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x2505c  ldc.i4.0
0x2505d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x25062  ldarg.0
0x25063  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x25068  ldc.i4.1
0x25069  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2506e  ldarg.0
0x2506f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x25074  ldnull
0x25075  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2507a  ldarg.0
0x2507b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x25080  ldstr    aName// "Name"
0x25085  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2508a  ldarg.0
  ... truncated ...
```
