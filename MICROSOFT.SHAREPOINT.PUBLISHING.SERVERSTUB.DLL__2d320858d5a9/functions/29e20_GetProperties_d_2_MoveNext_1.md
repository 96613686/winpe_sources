# <GetProperties>d__2::MoveNext_1

- ea: `0x29e20`
- end: `0x2a093`
- name: `<GetProperties>d__2::MoveNext_1`
- size: `627`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x11980`
- `0x29e20`
- `0x2a0c0`
- `0x2a120`

## string_xrefs

- `0x29edc`: `LastVersionCreated`
- `0x29f56`: `LastVersionCreated`
- `0x29fc2`: `LastVersionCreatedBy`
- `0x2a02f`: `LastVersionCreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x29e20  ldarg.0
0x29e21  ldfld    int32 <GetProperties>d__2::<>1__state
0x29e26  stloc.1
0x29e27  ldloc.1
0x29e28  switch   loc_29E46, loc_2A086, loc_29EB0, loc_29FA9, loc_2A07F
0x29e41  br       loc_2A086
0x29e46  ldarg.0
0x29e47  ldc.i4.m1
0x29e48  stfld    int32 <GetProperties>d__2::<>1__state
0x29e4d  ldarg.0
0x29e4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2::proxyContext
0x29e53  brtrue.s loc_29E60
0x29e55  ldstr    aProxycontext// "proxyContext"
0x29e5a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x29e5f  throw
0x29e60  ldarg.0
0x29e61  ldarg.0
0x29e62  ldfld    class Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter <GetProperties>d__2::<>4__this
0x29e67  ldarg.0
0x29e68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2::proxyContext
0x29e6d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::<>n__FabricatedMethod6(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x29e72  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x29e77  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x29e7c  ldarg.0
0x29e7d  ldc.i4.1
0x29e7e  stfld    int32 <GetProperties>d__2::<>1__state
0x29e83  br.s     loc_29EB7
0x29e85  ldarg.0
0x29e86  ldarg.0
0x29e87  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x29e8c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x29e91  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<item>5__3
0x29e96  ldarg.0
0x29e97  ldarg.0
0x29e98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<item>5__3
0x29e9d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x29ea2  ldarg.0
0x29ea3  ldc.i4.2
0x29ea4  stfld    int32 <GetProperties>d__2::<>1__state
0x29ea9  ldc.i4.1
0x29eaa  stloc.0
0x29eab  leave    loc_2A091
0x29eb0  ldarg.0
0x29eb1  ldc.i4.1
0x29eb2  stfld    int32 <GetProperties>d__2::<>1__state
0x29eb7  ldarg.0
0x29eb8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x29ebd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x29ec2  brtrue.s loc_29E85
0x29ec4  ldarg.0
0x29ec5  call     instance void <GetProperties>d__2::<>m__Finally5()
0x29eca  ldarg.0
0x29ecb  ldarg.0
0x29ecc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x29ed1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29ed6  ldarg.0
0x29ed7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29edc  ldstr    aLastversioncre// "LastVersionCreated"
0x29ee1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x29ee6  ldarg.0
0x29ee7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29eec  ldc.i4.0
0x29eed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x29ef2  ldarg.0
0x29ef3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29ef8  ldc.i4.1
0x29ef9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x29efe  ldarg.0
0x29eff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f04  ldc.i4.0
0x29f05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x29f0a  ldarg.0
0x29f0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f10  ldtoken  [mscorlib]System.DateTime
0x29f15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29f1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x29f1f  ldarg.0
0x29f20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f25  ldc.i4.0
0x29f26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x29f2b  ldarg.0
0x29f2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f31  ldc.i4.1
0x29f32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x29f37  ldarg.0
0x29f38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f3d  ldloca.s 2
0x29f3f  initobj  [mscorlib]System.DateTime
0x29f45  ldloc.2
0x29f46  box      [mscorlib]System.DateTime
0x29f4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x29f50  ldarg.0
0x29f51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f56  ldstr    aLastversioncre// "LastVersionCreated"
0x29f5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x29f60  ldarg.0
0x29f61  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f66  ldnull
0x29f67  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x29f6c  ldarg.0
0x29f6d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f72  ldc.i4.0
0x29f73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x29f78  ldarg.0
0x29f79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f7e  ldc.i4.1
0x29f7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x29f84  ldarg.0
0x29f85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f8a  ldc.i4.0
0x29f8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x29f90  ldarg.0
0x29f91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x29f96  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x29f9b  ldarg.0
0x29f9c  ldc.i4.3
0x29f9d  stfld    int32 <GetProperties>d__2::<>1__state
0x29fa2  ldc.i4.1
0x29fa3  stloc.0
0x29fa4  leave    loc_2A091
0x29fa9  ldarg.0
0x29faa  ldc.i4.m1
0x29fab  stfld    int32 <GetProperties>d__2::<>1__state
0x29fb0  ldarg.0
0x29fb1  ldarg.0
0x29fb2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x29fb7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x29fbc  ldarg.0
0x29fbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x29fc2  ldstr    aLastversioncre_0// "LastVersionCreatedBy"
0x29fc7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x29fcc  ldarg.0
0x29fcd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x29fd2  ldc.i4.0
0x29fd3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x29fd8  ldarg.0
0x29fd9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x29fde  ldc.i4.1
0x29fdf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x29fe4  ldarg.0
0x29fe5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x29fea  ldc.i4.0
0x29feb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x29ff0  ldarg.0
0x29ff1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x29ff6  ldtoken  [mscorlib]System.String
0x29ffb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a000  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2a005  ldarg.0
0x2a006  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a00b  ldc.i4.0
0x2a00c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2a011  ldarg.0
0x2a012  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a017  ldc.i4.1
0x2a018  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2a01d  ldarg.0
0x2a01e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a023  ldnull
0x2a024  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2a029  ldarg.0
0x2a02a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a02f  ldstr    aLastversioncre_0// "LastVersionCreatedBy"
0x2a034  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2a039  ldarg.0
0x2a03a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a03f  ldnull
0x2a040  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2a045  ldarg.0
0x2a046  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a04b  ldc.i4.0
0x2a04c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2a051  ldarg.0
0x2a052  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a057  ldc.i4.1
0x2a058  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2a05d  ldarg.0
0x2a05e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a063  ldc.i4.0
0x2a064  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2a069  ldarg.0
0x2a06a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2a06f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x2a074  ldarg.0
0x2a075  ldc.i4.4
0x2a076  stfld    int32 <GetProperties>d__2::<>1__state
0x2a07b  ldc.i4.1
0x2a07c  stloc.0
0x2a07d  leave.s  loc_2A091
0x2a07f  ldarg.0
0x2a080  ldc.i4.m1
0x2a081  stfld    int32 <GetProperties>d__2::<>1__state
0x2a086  ldc.i4.0
0x2a087  stloc.0
0x2a088  leave.s  loc_2A091
0x2a08a  ldarg.0
0x2a08b  call     instance void <GetProperties>d__2::System.IDisposable.Dispose()
0x2a090  endfinally
0x2a091  ldloc.0
0x2a092  ret
```
