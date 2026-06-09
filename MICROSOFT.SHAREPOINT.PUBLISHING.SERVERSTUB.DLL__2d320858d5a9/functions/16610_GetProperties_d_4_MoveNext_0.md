# <GetProperties>d__4::MoveNext_0

- ea: `0x16610`
- end: `0x16a47`
- name: `<GetProperties>d__4::MoveNext_0`
- size: `1079`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x2d80`
- `0x16610`
- `0x16a70`
- `0x16ad0`

## pseudocode

```c

```

## disassembly

```asm
0x16610  ldarg.0
0x16611  ldfld    int32 <GetProperties>d__4::<>1__state
0x16616  stloc.1
0x16617  ldloc.1
0x16618  switch   loc_1663E, loc_16A3A, loc_166A8, loc_16799, loc_16877, loc_1695D, loc_16A33
0x16639  br       loc_16A3A
0x1663e  ldarg.0
0x1663f  ldc.i4.m1
0x16640  stfld    int32 <GetProperties>d__4::<>1__state
0x16645  ldarg.0
0x16646  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x1664b  brtrue.s loc_16658
0x1664d  ldstr    aProxycontext// "proxyContext"
0x16652  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16657  throw
0x16658  ldarg.0
0x16659  ldarg.0
0x1665a  ldfld    class Microsoft.SharePoint.Publishing.DesignPackageInfoValueTypeConverter <GetProperties>d__4::<>4__this
0x1665f  ldarg.0
0x16660  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x16665  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.DesignPackageInfoValueTypeConverter::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x1666a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1666f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x16674  ldarg.0
0x16675  ldc.i4.1
0x16676  stfld    int32 <GetProperties>d__4::<>1__state
0x1667b  br.s     loc_166AF
0x1667d  ldarg.0
0x1667e  ldarg.0
0x1667f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x16684  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x16689  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x1668e  ldarg.0
0x1668f  ldarg.0
0x16690  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x16695  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x1669a  ldarg.0
0x1669b  ldc.i4.2
0x1669c  stfld    int32 <GetProperties>d__4::<>1__state
0x166a1  ldc.i4.1
0x166a2  stloc.0
0x166a3  leave    loc_16A45
0x166a8  ldarg.0
0x166a9  ldc.i4.1
0x166aa  stfld    int32 <GetProperties>d__4::<>1__state
0x166af  ldarg.0
0x166b0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x166b5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x166ba  brtrue.s loc_1667D
0x166bc  ldarg.0
0x166bd  call     instance void <GetProperties>d__4::<>m__Finally7()
0x166c2  ldarg.0
0x166c3  ldarg.0
0x166c4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x166c9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x166ce  ldarg.0
0x166cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x166d4  ldstr    aMajorversion// "MajorVersion"
0x166d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x166de  ldarg.0
0x166df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x166e4  ldc.i4.0
0x166e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x166ea  ldarg.0
0x166eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x166f0  ldc.i4.1
0x166f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x166f6  ldarg.0
0x166f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x166fc  ldc.i4.0
0x166fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x16702  ldarg.0
0x16703  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x16708  ldtoken  [mscorlib]System.Int32
0x1670d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16712  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x16717  ldarg.0
0x16718  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x1671d  ldc.i4.0
0x1671e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x16723  ldarg.0
0x16724  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x16729  ldc.i4.1
0x1672a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1672f  ldarg.0
0x16730  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x16735  ldc.i4.0
0x16736  box      [mscorlib]System.Int32
0x1673b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x16740  ldarg.0
0x16741  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x16746  ldstr    aMajorversion// "MajorVersion"
0x1674b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x16750  ldarg.0
0x16751  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x16756  ldnull
0x16757  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1675c  ldarg.0
0x1675d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x16762  ldc.i4.0
0x16763  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x16768  ldarg.0
0x16769  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x1676e  ldc.i4.0
0x1676f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x16774  ldarg.0
0x16775  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x1677a  ldc.i4.0
0x1677b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x16780  ldarg.0
0x16781  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x16786  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x1678b  ldarg.0
0x1678c  ldc.i4.3
0x1678d  stfld    int32 <GetProperties>d__4::<>1__state
0x16792  ldc.i4.1
0x16793  stloc.0
0x16794  leave    loc_16A45
0x16799  ldarg.0
0x1679a  ldc.i4.m1
0x1679b  stfld    int32 <GetProperties>d__4::<>1__state
0x167a0  ldarg.0
0x167a1  ldarg.0
0x167a2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x167a7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x167ac  ldarg.0
0x167ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x167b2  ldstr    aMinorversion// "MinorVersion"
0x167b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x167bc  ldarg.0
0x167bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x167c2  ldc.i4.0
0x167c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x167c8  ldarg.0
0x167c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x167ce  ldc.i4.1
0x167cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x167d4  ldarg.0
0x167d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x167da  ldc.i4.0
0x167db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x167e0  ldarg.0
0x167e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x167e6  ldtoken  [mscorlib]System.Int32
0x167eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x167f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x167f5  ldarg.0
0x167f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x167fb  ldc.i4.0
0x167fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x16801  ldarg.0
0x16802  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x16807  ldc.i4.1
0x16808  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1680d  ldarg.0
0x1680e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x16813  ldc.i4.0
0x16814  box      [mscorlib]System.Int32
0x16819  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1681e  ldarg.0
0x1681f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x16824  ldstr    aMinorversion// "MinorVersion"
0x16829  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1682e  ldarg.0
0x1682f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x16834  ldnull
0x16835  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1683a  ldarg.0
0x1683b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x16840  ldc.i4.0
0x16841  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x16846  ldarg.0
0x16847  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x1684c  ldc.i4.0
0x1684d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x16852  ldarg.0
0x16853  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x16858  ldc.i4.0
0x16859  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1685e  ldarg.0
0x1685f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x16864  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x16869  ldarg.0
0x1686a  ldc.i4.4
0x1686b  stfld    int32 <GetProperties>d__4::<>1__state
0x16870  ldc.i4.1
0x16871  stloc.0
0x16872  leave    loc_16A45
0x16877  ldarg.0
0x16878  ldc.i4.m1
0x16879  stfld    int32 <GetProperties>d__4::<>1__state
0x1687e  ldarg.0
0x1687f  ldarg.0
0x16880  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x16885  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1688a  ldarg.0
0x1688b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x16890  ldstr    aPackageguid// "PackageGuid"
0x16895  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1689a  ldarg.0
0x1689b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x168a0  ldc.i4.0
0x168a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x168a6  ldarg.0
0x168a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x168ac  ldc.i4.1
0x168ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x168b2  ldarg.0
0x168b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x168b8  ldc.i4.0
0x168b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x168be  ldarg.0
0x168bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x168c4  ldtoken  [mscorlib]System.Guid
0x168c9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x168ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x168d3  ldarg.0
0x168d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x168d9  ldc.i4.0
0x168da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x168df  ldarg.0
0x168e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x168e5  ldc.i4.1
0x168e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x168eb  ldarg.0
0x168ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x168f1  ldloca.s 2
0x168f3  initobj  [mscorlib]System.Guid
0x168f9  ldloc.2
0x168fa  box      [mscorlib]System.Guid
0x168ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x16904  ldarg.0
0x16905  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1690a  ldstr    aPackageguid// "PackageGuid"
0x1690f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x16914  ldarg.0
0x16915  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1691a  ldnull
0x1691b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x16920  ldarg.0
0x16921  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x16926  ldc.i4.0
0x16927  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1692c  ldarg.0
0x1692d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x16932  ldc.i4.0
0x16933  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x16938  ldarg.0
0x16939  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1693e  ldc.i4.0
0x1693f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x16944  ldarg.0
0x16945  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1694a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x1694f  ldarg.0
0x16950  ldc.i4.5
0x16951  stfld    int32 <GetProperties>d__4::<>1__state
0x16956  ldc.i4.1
0x16957  stloc.0
0x16958  leave    loc_16A45
0x1695d  ldarg.0
0x1695e  ldc.i4.m1
0x1695f  stfld    int32 <GetProperties>d__4::<>1__state
0x16964  ldarg.0
0x16965  ldarg.0
0x16966  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1696b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x16970  ldarg.0
0x16971  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x16976  ldstr    aPackagename// "PackageName"
0x1697b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x16980  ldarg.0
0x16981  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x16986  ldc.i4.0
0x16987  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1698c  ldarg.0
0x1698d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x16992  ldc.i4.1
0x16993  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16998  ldarg.0
0x16999  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x1699e  ldc.i4.0
0x1699f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x169a4  ldarg.0
0x169a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x169aa  ldtoken  [mscorlib]System.String
0x169af  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x169b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x169b9  ldarg.0
0x169ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x169bf  ldc.i4.0
0x169c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x169c5  ldarg.0
0x169c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x169cb  ldc.i4.1
0x169cc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x169d1  ldarg.0
0x169d2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x169d7  ldnull
0x169d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
  ... truncated ...
```
