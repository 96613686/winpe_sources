# <GetProperties>d__2::MoveNext

- ea: `0x158e0`
- end: `0x15b4b`
- name: `<GetProperties>d__2::MoveNext`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x20e0`
- `0x158e0`
- `0x15b70`
- `0x15bd0`

## pseudocode

```c

```

## disassembly

```asm
0x158e0  ldarg.0
0x158e1  ldfld    int32 <GetProperties>d__2::<>1__state
0x158e6  stloc.1
0x158e7  ldloc.1
0x158e8  switch   loc_15906, loc_15B3E, loc_15970, loc_15A61, loc_15B37
0x15901  br       loc_15B3E
0x15906  ldarg.0
0x15907  ldc.i4.m1
0x15908  stfld    int32 <GetProperties>d__2::<>1__state
0x1590d  ldarg.0
0x1590e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2::proxyContext
0x15913  brtrue.s loc_15920
0x15915  ldstr    aProxycontext// "proxyContext"
0x1591a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1591f  throw
0x15920  ldarg.0
0x15921  ldarg.0
0x15922  ldfld    class Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter <GetProperties>d__2::<>4__this
0x15927  ldarg.0
0x15928  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2::proxyContext
0x1592d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::<>n__FabricatedMethod6(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x15932  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x15937  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x1593c  ldarg.0
0x1593d  ldc.i4.1
0x1593e  stfld    int32 <GetProperties>d__2::<>1__state
0x15943  br.s     loc_15977
0x15945  ldarg.0
0x15946  ldarg.0
0x15947  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x1594c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x15951  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<item>5__3
0x15956  ldarg.0
0x15957  ldarg.0
0x15958  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<item>5__3
0x1595d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x15962  ldarg.0
0x15963  ldc.i4.2
0x15964  stfld    int32 <GetProperties>d__2::<>1__state
0x15969  ldc.i4.1
0x1596a  stloc.0
0x1596b  leave    loc_15B49
0x15970  ldarg.0
0x15971  ldc.i4.1
0x15972  stfld    int32 <GetProperties>d__2::<>1__state
0x15977  ldarg.0
0x15978  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x1597d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15982  brtrue.s loc_15945
0x15984  ldarg.0
0x15985  call     instance void <GetProperties>d__2::<>m__Finally5()
0x1598a  ldarg.0
0x1598b  ldarg.0
0x1598c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15991  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x15996  ldarg.0
0x15997  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x1599c  ldstr    aSitestatus// "SiteStatus"
0x159a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x159a6  ldarg.0
0x159a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x159ac  ldc.i4.0
0x159ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x159b2  ldarg.0
0x159b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x159b8  ldc.i4.1
0x159b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x159be  ldarg.0
0x159bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x159c4  ldc.i4.0
0x159c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x159ca  ldarg.0
0x159cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x159d0  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteStatus
0x159d5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x159df  ldarg.0
0x159e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x159e5  ldc.i4.0
0x159e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x159eb  ldarg.0
0x159ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x159f1  ldc.i4.1
0x159f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x159f7  ldarg.0
0x159f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x159fd  ldc.i4.0
0x159fe  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteStatus
0x15a03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15a08  ldarg.0
0x15a09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x15a0e  ldstr    aSitestatus// "SiteStatus"
0x15a13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15a18  ldarg.0
0x15a19  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x15a1e  ldnull
0x15a1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x15a24  ldarg.0
0x15a25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x15a2a  ldc.i4.0
0x15a2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x15a30  ldarg.0
0x15a31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x15a36  ldc.i4.0
0x15a37  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x15a3c  ldarg.0
0x15a3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x15a42  ldc.i4.0
0x15a43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x15a48  ldarg.0
0x15a49  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x15a4e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x15a53  ldarg.0
0x15a54  ldc.i4.3
0x15a55  stfld    int32 <GetProperties>d__2::<>1__state
0x15a5a  ldc.i4.1
0x15a5b  stloc.0
0x15a5c  leave    loc_15B49
0x15a61  ldarg.0
0x15a62  ldc.i4.m1
0x15a63  stfld    int32 <GetProperties>d__2::<>1__state
0x15a68  ldarg.0
0x15a69  ldarg.0
0x15a6a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15a6f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15a74  ldarg.0
0x15a75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15a7a  ldstr    aSiteurl// "SiteUrl"
0x15a7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x15a84  ldarg.0
0x15a85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15a8a  ldc.i4.0
0x15a8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x15a90  ldarg.0
0x15a91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15a96  ldc.i4.1
0x15a97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15a9c  ldarg.0
0x15a9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15aa2  ldc.i4.0
0x15aa3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x15aa8  ldarg.0
0x15aa9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15aae  ldtoken  [mscorlib]System.String
0x15ab3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ab8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x15abd  ldarg.0
0x15abe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15ac3  ldc.i4.0
0x15ac4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x15ac9  ldarg.0
0x15aca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15acf  ldc.i4.1
0x15ad0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x15ad5  ldarg.0
0x15ad6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15adb  ldnull
0x15adc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15ae1  ldarg.0
0x15ae2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15ae7  ldstr    aSiteurl// "SiteUrl"
0x15aec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15af1  ldarg.0
0x15af2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15af7  ldnull
0x15af8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x15afd  ldarg.0
0x15afe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15b03  ldc.i4.0
0x15b04  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x15b09  ldarg.0
0x15b0a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15b0f  ldc.i4.0
0x15b10  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x15b15  ldarg.0
0x15b16  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15b1b  ldc.i4.0
0x15b1c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x15b21  ldarg.0
0x15b22  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x15b27  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x15b2c  ldarg.0
0x15b2d  ldc.i4.4
0x15b2e  stfld    int32 <GetProperties>d__2::<>1__state
0x15b33  ldc.i4.1
0x15b34  stloc.0
0x15b35  leave.s  loc_15B49
0x15b37  ldarg.0
0x15b38  ldc.i4.m1
0x15b39  stfld    int32 <GetProperties>d__2::<>1__state
0x15b3e  ldc.i4.0
0x15b3f  stloc.0
0x15b40  leave.s  loc_15B49
0x15b42  ldarg.0
0x15b43  call     instance void <GetProperties>d__2::System.IDisposable.Dispose()
0x15b48  endfinally
0x15b49  ldloc.0
0x15b4a  ret
```
