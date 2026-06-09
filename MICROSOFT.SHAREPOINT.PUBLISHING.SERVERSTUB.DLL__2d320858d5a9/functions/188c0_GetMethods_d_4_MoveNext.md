# <GetMethods>d__4::MoveNext

- ea: `0x188c0`
- end: `0x18c19`
- name: `<GetMethods>d__4::MoveNext`
- size: `857`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x4ca0`
- `0x188c0`
- `0x18c40`
- `0x18ca0`

## pseudocode

```c

```

## disassembly

```asm
0x188c0  ldarg.0
0x188c1  ldfld    int32 <GetMethods>d__4::<>1__state
0x188c6  stloc.1
0x188c7  ldloc.1
0x188c8  switch   loc_188E6, loc_18C0C, loc_18950, loc_18A37, loc_18C05
0x188e1  br       loc_18C0C
0x188e6  ldarg.0
0x188e7  ldc.i4.m1
0x188e8  stfld    int32 <GetMethods>d__4::<>1__state
0x188ed  ldarg.0
0x188ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__4::proxyContext
0x188f3  brtrue.s loc_18900
0x188f5  ldstr    aProxycontext// "proxyContext"
0x188fa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x188ff  throw
0x18900  ldarg.0
0x18901  ldarg.0
0x18902  ldfld    class Microsoft.SharePoint.Publishing.EmbedServiceServerStub <GetMethods>d__4::<>4__this
0x18907  ldarg.0
0x18908  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__4::proxyContext
0x1890d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.EmbedServiceServerStub::<>n__FabricatedMethod9(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x18912  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x18917  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x1891c  ldarg.0
0x1891d  ldc.i4.1
0x1891e  stfld    int32 <GetMethods>d__4::<>1__state
0x18923  br.s     loc_18957
0x18925  ldarg.0
0x18926  ldarg.0
0x18927  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x1892c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x18931  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<itemBase>5__5
0x18936  ldarg.0
0x18937  ldarg.0
0x18938  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<itemBase>5__5
0x1893d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x18942  ldarg.0
0x18943  ldc.i4.2
0x18944  stfld    int32 <GetMethods>d__4::<>1__state
0x18949  ldc.i4.1
0x1894a  stloc.0
0x1894b  leave    loc_18C17
0x18950  ldarg.0
0x18951  ldc.i4.1
0x18952  stfld    int32 <GetMethods>d__4::<>1__state
0x18957  ldarg.0
0x18958  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x1895d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18962  brtrue.s loc_18925
0x18964  ldarg.0
0x18965  call     instance void <GetMethods>d__4::<>m__Finally8()
0x1896a  ldarg.0
0x1896b  ldarg.0
0x1896c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x18971  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x18976  ldarg.0
0x18977  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x1897c  ldstr    aCtor// ".ctor"
0x18981  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x18986  ldarg.0
0x18987  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x1898c  ldc.i4.0
0x1898d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x18992  ldarg.0
0x18993  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x18998  ldc.i4.0
0x18999  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1899e  ldarg.0
0x1899f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x189a4  ldc.i4   0xFFFFFFF
0x189a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x189ae  ldarg.0
0x189af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x189b4  ldstr    aCtor// ".ctor"
0x189b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x189be  ldarg.0
0x189bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x189c4  ldc.i4.0
0x189c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x189ca  ldarg.0
0x189cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x189d0  ldnull
0x189d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x189d6  ldarg.0
0x189d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x189dc  ldc.i4.0
0x189dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x189e2  ldarg.0
0x189e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x189e8  ldc.i4.0
0x189e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x189ee  ldarg.0
0x189ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x189f4  ldc.i4.0
0x189f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x189fa  ldarg.0
0x189fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x18a00  ldc.i4.0
0x18a01  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18a06  ldarg.0
0x18a07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x18a0c  ldc.i4.1
0x18a0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x18a12  ldarg.0
0x18a13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x18a18  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x18a1d  ldarg.0
0x18a1e  ldarg.0
0x18a1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x18a24  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x18a29  ldarg.0
0x18a2a  ldc.i4.3
0x18a2b  stfld    int32 <GetMethods>d__4::<>1__state
0x18a30  ldc.i4.1
0x18a31  stloc.0
0x18a32  leave    loc_18C17
0x18a37  ldarg.0
0x18a38  ldc.i4.m1
0x18a39  stfld    int32 <GetMethods>d__4::<>1__state
0x18a3e  ldarg.0
0x18a3f  ldarg.0
0x18a40  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x18a45  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18a4a  ldarg.0
0x18a4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18a50  ldstr    aEmbeddata// "EmbedData"
0x18a55  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x18a5a  ldarg.0
0x18a5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18a60  ldc.i4.0
0x18a61  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x18a66  ldarg.0
0x18a67  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18a6c  ldc.i4.1
0x18a6d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x18a72  ldarg.0
0x18a73  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18a78  ldc.i4   0xFFFFFFF
0x18a7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x18a82  ldarg.0
0x18a83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18a88  ldstr    aEmbeddata// "EmbedData"
0x18a8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x18a92  ldarg.0
0x18a93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18a98  ldc.i4.0
0x18a99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x18a9e  ldarg.0
0x18a9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18aa4  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1
0x18aa9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18aae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x18ab3  ldarg.0
0x18ab4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18ab9  ldc.i4.4
0x18aba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18abf  ldarg.0
0x18ac0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18ac5  ldc.i4.0
0x18ac6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x18acb  ldarg.0
0x18acc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18ad1  ldc.i4.0
0x18ad2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x18ad7  ldarg.0
0x18ad8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18add  ldc.i4.0
0x18ade  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18ae3  ldarg.0
0x18ae4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18ae9  ldc.i4.1
0x18aea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x18aef  ldarg.0
0x18af0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x18af5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x18afa  ldarg.0
0x18afb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x18b00  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x18b05  ldarg.0
0x18b06  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x18b0b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b10  ldarg.0
0x18b11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b16  ldstr    aUrl_0// "url"
0x18b1b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x18b20  ldarg.0
0x18b21  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b26  ldc.i4.0
0x18b27  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x18b2c  ldarg.0
0x18b2d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b32  ldtoken  [mscorlib]System.String
0x18b37  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18b3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x18b41  ldarg.0
0x18b42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b47  ldc.i4.1
0x18b48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18b4d  ldarg.0
0x18b4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b53  ldc.i4.0
0x18b54  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x18b59  ldarg.0
0x18b5a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b5f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x18b64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x18b69  ldarg.0
0x18b6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal2
0x18b6f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x18b74  ldarg.0
0x18b75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x18b7a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x18b7f  ldarg.0
0x18b80  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x18b85  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18b8a  ldarg.0
0x18b8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18b90  ldstr    aVersion// "version"
0x18b95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x18b9a  ldarg.0
0x18b9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18ba0  ldc.i4.0
0x18ba1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x18ba6  ldarg.0
0x18ba7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18bac  ldtoken  [mscorlib]System.Int32
0x18bb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18bb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x18bbb  ldarg.0
0x18bbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18bc1  ldc.i4.1
0x18bc2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18bc7  ldarg.0
0x18bc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18bcd  ldc.i4.0
0x18bce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x18bd3  ldarg.0
0x18bd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18bd9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x18bde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x18be3  ldarg.0
0x18be4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x18be9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x18bee  ldarg.0
0x18bef  ldarg.0
0x18bf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x18bf5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x18bfa  ldarg.0
0x18bfb  ldc.i4.4
0x18bfc  stfld    int32 <GetMethods>d__4::<>1__state
0x18c01  ldc.i4.1
0x18c02  stloc.0
0x18c03  leave.s  loc_18C17
0x18c05  ldarg.0
0x18c06  ldc.i4.m1
0x18c07  stfld    int32 <GetMethods>d__4::<>1__state
0x18c0c  ldc.i4.0
0x18c0d  stloc.0
0x18c0e  leave.s  loc_18C17
0x18c10  ldarg.0
0x18c11  call     instance void <GetMethods>d__4::System.IDisposable.Dispose()
0x18c16  endfinally
0x18c17  ldloc.0
0x18c18  ret
```
