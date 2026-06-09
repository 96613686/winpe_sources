# <GetProperties>d__7::MoveNext

- ea: `0x18d40`
- end: `0x19411`
- name: `<GetProperties>d__7::MoveNext`
- size: `1745`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x5170`
- `0x18d40`
- `0x19440`
- `0x194a0`

## pseudocode

```c

```

## disassembly

```asm
0x18d40  ldarg.0
0x18d41  ldfld    int32 <GetProperties>d__7::<>1__state
0x18d46  stloc.1
0x18d47  ldloc.1
0x18d48  switch   loc_18D7A, loc_19404, loc_18DE4, loc_18ED0, loc_18FAE, loc_1908C, loc_1916A, loc_19243, loc_19321, loc_193FD
0x18d75  br       loc_19404
0x18d7a  ldarg.0
0x18d7b  ldc.i4.m1
0x18d7c  stfld    int32 <GetProperties>d__7::<>1__state
0x18d81  ldarg.0
0x18d82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7::proxyContext
0x18d87  brtrue.s loc_18D94
0x18d89  ldstr    aProxycontext// "proxyContext"
0x18d8e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18d93  throw
0x18d94  ldarg.0
0x18d95  ldarg.0
0x18d96  ldfld    class Microsoft.SharePoint.Publishing.ImageRenditionValueTypeConverter <GetProperties>d__7::<>4__this
0x18d9b  ldarg.0
0x18d9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7::proxyContext
0x18da1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.ImageRenditionValueTypeConverter::<>n__FabricatedMethodb(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext name)
0x18da6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x18dab  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7::<>7__wrap9
0x18db0  ldarg.0
0x18db1  ldc.i4.1
0x18db2  stfld    int32 <GetProperties>d__7::<>1__state
0x18db7  br.s     loc_18DEB
0x18db9  ldarg.0
0x18dba  ldarg.0
0x18dbb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7::<>7__wrap9
0x18dc0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x18dc5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<item>5__8
0x18dca  ldarg.0
0x18dcb  ldarg.0
0x18dcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<item>5__8
0x18dd1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x18dd6  ldarg.0
0x18dd7  ldc.i4.2
0x18dd8  stfld    int32 <GetProperties>d__7::<>1__state
0x18ddd  ldc.i4.1
0x18dde  stloc.0
0x18ddf  leave    loc_1940F
0x18de4  ldarg.0
0x18de5  ldc.i4.1
0x18de6  stfld    int32 <GetProperties>d__7::<>1__state
0x18deb  ldarg.0
0x18dec  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7::<>7__wrap9
0x18df1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18df6  brtrue.s loc_18DB9
0x18df8  ldarg.0
0x18df9  call     instance void <GetProperties>d__7::<>m__Finallya()
0x18dfe  ldarg.0
0x18dff  ldarg.0
0x18e00  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x18e05  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e0a  ldarg.0
0x18e0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e10  ldstr    aGroup// "Group"
0x18e15  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x18e1a  ldarg.0
0x18e1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e20  ldc.i4.0
0x18e21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x18e26  ldarg.0
0x18e27  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e2c  ldc.i4.1
0x18e2d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18e32  ldarg.0
0x18e33  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e38  ldc.i4.0
0x18e39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x18e3e  ldarg.0
0x18e3f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e44  ldtoken  [mscorlib]System.String
0x18e49  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18e4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x18e53  ldarg.0
0x18e54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e59  ldc.i4.0
0x18e5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x18e5f  ldarg.0
0x18e60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e65  ldc.i4.1
0x18e66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x18e6b  ldarg.0
0x18e6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e71  ldnull
0x18e72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x18e77  ldarg.0
0x18e78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e7d  ldstr    aGroup// "Group"
0x18e82  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x18e87  ldarg.0
0x18e88  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e8d  ldnull
0x18e8e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x18e93  ldarg.0
0x18e94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18e99  ldc.i4.0
0x18e9a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18e9f  ldarg.0
0x18ea0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18ea5  ldc.i4.0
0x18ea6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x18eab  ldarg.0
0x18eac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18eb1  ldc.i4.0
0x18eb2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x18eb7  ldarg.0
0x18eb8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x18ebd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x18ec2  ldarg.0
0x18ec3  ldc.i4.3
0x18ec4  stfld    int32 <GetProperties>d__7::<>1__state
0x18ec9  ldc.i4.1
0x18eca  stloc.0
0x18ecb  leave    loc_1940F
0x18ed0  ldarg.0
0x18ed1  ldc.i4.m1
0x18ed2  stfld    int32 <GetProperties>d__7::<>1__state
0x18ed7  ldarg.0
0x18ed8  ldarg.0
0x18ed9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x18ede  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18ee3  ldarg.0
0x18ee4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18ee9  ldstr    aHeight// "Height"
0x18eee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x18ef3  ldarg.0
0x18ef4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18ef9  ldc.i4.0
0x18efa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x18eff  ldarg.0
0x18f00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f05  ldc.i4.1
0x18f06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18f0b  ldarg.0
0x18f0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f11  ldc.i4.0
0x18f12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x18f17  ldarg.0
0x18f18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f1d  ldtoken  [mscorlib]System.Int32
0x18f22  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18f27  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x18f2c  ldarg.0
0x18f2d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f32  ldc.i4.0
0x18f33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x18f38  ldarg.0
0x18f39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f3e  ldc.i4.1
0x18f3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x18f44  ldarg.0
0x18f45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f4a  ldc.i4.0
0x18f4b  box      [mscorlib]System.Int32
0x18f50  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x18f55  ldarg.0
0x18f56  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f5b  ldstr    aHeight// "Height"
0x18f60  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x18f65  ldarg.0
0x18f66  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f6b  ldnull
0x18f6c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x18f71  ldarg.0
0x18f72  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f77  ldc.i4.0
0x18f78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18f7d  ldarg.0
0x18f7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f83  ldc.i4.0
0x18f84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x18f89  ldarg.0
0x18f8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f8f  ldc.i4.0
0x18f90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x18f95  ldarg.0
0x18f96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x18f9b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x18fa0  ldarg.0
0x18fa1  ldc.i4.4
0x18fa2  stfld    int32 <GetProperties>d__7::<>1__state
0x18fa7  ldc.i4.1
0x18fa8  stloc.0
0x18fa9  leave    loc_1940F
0x18fae  ldarg.0
0x18faf  ldc.i4.m1
0x18fb0  stfld    int32 <GetProperties>d__7::<>1__state
0x18fb5  ldarg.0
0x18fb6  ldarg.0
0x18fb7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x18fbc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x18fc1  ldarg.0
0x18fc2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x18fc7  ldstr    aId// "Id"
0x18fcc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x18fd1  ldarg.0
0x18fd2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x18fd7  ldc.i4.0
0x18fd8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x18fdd  ldarg.0
0x18fde  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x18fe3  ldc.i4.1
0x18fe4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18fe9  ldarg.0
0x18fea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x18fef  ldc.i4.0
0x18ff0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x18ff5  ldarg.0
0x18ff6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x18ffb  ldtoken  [mscorlib]System.Int32
0x19000  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19005  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1900a  ldarg.0
0x1900b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x19010  ldc.i4.1
0x19011  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x19016  ldarg.0
0x19017  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1901c  ldc.i4.1
0x1901d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x19022  ldarg.0
0x19023  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x19028  ldc.i4.0
0x19029  box      [mscorlib]System.Int32
0x1902e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x19033  ldarg.0
0x19034  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x19039  ldstr    aId// "Id"
0x1903e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x19043  ldarg.0
0x19044  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x19049  ldnull
0x1904a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1904f  ldarg.0
0x19050  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x19055  ldc.i4.0
0x19056  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1905b  ldarg.0
0x1905c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x19061  ldc.i4.0
0x19062  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x19067  ldarg.0
0x19068  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1906d  ldc.i4.0
0x1906e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x19073  ldarg.0
0x19074  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x19079  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x1907e  ldarg.0
0x1907f  ldc.i4.5
0x19080  stfld    int32 <GetProperties>d__7::<>1__state
0x19085  ldc.i4.1
0x19086  stloc.0
0x19087  leave    loc_1940F
0x1908c  ldarg.0
0x1908d  ldc.i4.m1
0x1908e  stfld    int32 <GetProperties>d__7::<>1__state
0x19093  ldarg.0
0x19094  ldarg.0
0x19095  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1909a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1909f  ldarg.0
0x190a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x190a5  ldstr    aIdcsom// "IdCsom"
0x190aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x190af  ldarg.0
0x190b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x190b5  ldc.i4.0
0x190b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x190bb  ldarg.0
0x190bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x190c1  ldc.i4.1
0x190c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x190c7  ldarg.0
0x190c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x190cd  ldc.i4.0
0x190ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x190d3  ldarg.0
0x190d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x190d9  ldtoken  [mscorlib]System.Int32
0x190de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x190e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x190e8  ldarg.0
0x190e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x190ee  ldc.i4.0
0x190ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x190f4  ldarg.0
0x190f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x190fa  ldc.i4.1
0x190fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x19100  ldarg.0
0x19101  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x19106  ldc.i4.0
0x19107  box      [mscorlib]System.Int32
0x1910c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x19111  ldarg.0
0x19112  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
  ... truncated ...
```
