# <GetProperties>d__3::MoveNext

- ea: `0x161b0`
- end: `0x164f8`
- name: `<GetProperties>d__3::MoveNext`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x2990`
- `0x161b0`
- `0x16520`
- `0x16580`

## pseudocode

```c

```

## disassembly

```asm
0x161b0  ldarg.0
0x161b1  ldfld    int32 <GetProperties>d__3::<>1__state
0x161b6  stloc.1
0x161b7  ldloc.1
0x161b8  switch   loc_161DA, loc_164EB, loc_16244, loc_16330, loc_1640E, loc_164E4
0x161d5  br       loc_164EB
0x161da  ldarg.0
0x161db  ldc.i4.m1
0x161dc  stfld    int32 <GetProperties>d__3::<>1__state
0x161e1  ldarg.0
0x161e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x161e7  brtrue.s loc_161F4
0x161e9  ldstr    aProxycontext// "proxyContext"
0x161ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x161f3  throw
0x161f4  ldarg.0
0x161f5  ldarg.0
0x161f6  ldfld    class Microsoft.SharePoint.Publishing.CustomizableStringServerStub <GetProperties>d__3::<>4__this
0x161fb  ldarg.0
0x161fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x16201  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.CustomizableStringServerStub::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x16206  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1620b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x16210  ldarg.0
0x16211  ldc.i4.1
0x16212  stfld    int32 <GetProperties>d__3::<>1__state
0x16217  br.s     loc_1624B
0x16219  ldarg.0
0x1621a  ldarg.0
0x1621b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x16220  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x16225  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x1622a  ldarg.0
0x1622b  ldarg.0
0x1622c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x16231  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x16236  ldarg.0
0x16237  ldc.i4.2
0x16238  stfld    int32 <GetProperties>d__3::<>1__state
0x1623d  ldc.i4.1
0x1623e  stloc.0
0x1623f  leave    loc_164F6
0x16244  ldarg.0
0x16245  ldc.i4.1
0x16246  stfld    int32 <GetProperties>d__3::<>1__state
0x1624b  ldarg.0
0x1624c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x16251  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16256  brtrue.s loc_16219
0x16258  ldarg.0
0x16259  call     instance void <GetProperties>d__3::<>m__Finally6()
0x1625e  ldarg.0
0x1625f  ldarg.0
0x16260  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x16265  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1626a  ldarg.0
0x1626b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x16270  ldstr    aDefaultvalue// "DefaultValue"
0x16275  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1627a  ldarg.0
0x1627b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x16280  ldc.i4.0
0x16281  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x16286  ldarg.0
0x16287  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1628c  ldc.i4.1
0x1628d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16292  ldarg.0
0x16293  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x16298  ldc.i4.0
0x16299  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1629e  ldarg.0
0x1629f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x162a4  ldtoken  [mscorlib]System.String
0x162a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x162ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x162b3  ldarg.0
0x162b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x162b9  ldc.i4.1
0x162ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x162bf  ldarg.0
0x162c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x162c5  ldc.i4.1
0x162c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x162cb  ldarg.0
0x162cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x162d1  ldnull
0x162d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x162d7  ldarg.0
0x162d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x162dd  ldstr    aDefaultvalue// "DefaultValue"
0x162e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x162e7  ldarg.0
0x162e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x162ed  ldnull
0x162ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x162f3  ldarg.0
0x162f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x162f9  ldc.i4.0
0x162fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x162ff  ldarg.0
0x16300  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x16305  ldc.i4.0
0x16306  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1630b  ldarg.0
0x1630c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x16311  ldc.i4.0
0x16312  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x16317  ldarg.0
0x16318  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1631d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x16322  ldarg.0
0x16323  ldc.i4.3
0x16324  stfld    int32 <GetProperties>d__3::<>1__state
0x16329  ldc.i4.1
0x1632a  stloc.0
0x1632b  leave    loc_164F6
0x16330  ldarg.0
0x16331  ldc.i4.m1
0x16332  stfld    int32 <GetProperties>d__3::<>1__state
0x16337  ldarg.0
0x16338  ldarg.0
0x16339  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1633e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x16343  ldarg.0
0x16344  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x16349  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x1634e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x16353  ldarg.0
0x16354  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x16359  ldc.i4.0
0x1635a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1635f  ldarg.0
0x16360  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x16365  ldc.i4.1
0x16366  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1636b  ldarg.0
0x1636c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x16371  ldc.i4.0
0x16372  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x16377  ldarg.0
0x16378  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1637d  ldtoken  [mscorlib]System.Boolean
0x16382  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16387  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1638c  ldarg.0
0x1638d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x16392  ldc.i4.0
0x16393  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x16398  ldarg.0
0x16399  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1639e  ldc.i4.1
0x1639f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x163a4  ldarg.0
0x163a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x163aa  ldc.i4.0
0x163ab  box      [mscorlib]System.Boolean
0x163b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x163b5  ldarg.0
0x163b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x163bb  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x163c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x163c5  ldarg.0
0x163c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x163cb  ldnull
0x163cc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x163d1  ldarg.0
0x163d2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x163d7  ldc.i4.0
0x163d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x163dd  ldarg.0
0x163de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x163e3  ldc.i4.0
0x163e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x163e9  ldarg.0
0x163ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x163ef  ldc.i4.0
0x163f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x163f5  ldarg.0
0x163f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x163fb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x16400  ldarg.0
0x16401  ldc.i4.4
0x16402  stfld    int32 <GetProperties>d__3::<>1__state
0x16407  ldc.i4.1
0x16408  stloc.0
0x16409  leave    loc_164F6
0x1640e  ldarg.0
0x1640f  ldc.i4.m1
0x16410  stfld    int32 <GetProperties>d__3::<>1__state
0x16415  ldarg.0
0x16416  ldarg.0
0x16417  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1641c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x16421  ldarg.0
0x16422  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x16427  ldstr    aValue// "Value"
0x1642c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x16431  ldarg.0
0x16432  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x16437  ldc.i4.0
0x16438  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1643d  ldarg.0
0x1643e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x16443  ldc.i4.1
0x16444  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16449  ldarg.0
0x1644a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1644f  ldc.i4.0
0x16450  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x16455  ldarg.0
0x16456  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1645b  ldtoken  [mscorlib]System.String
0x16460  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16465  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1646a  ldarg.0
0x1646b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x16470  ldc.i4.0
0x16471  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x16476  ldarg.0
0x16477  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1647c  ldc.i4.1
0x1647d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x16482  ldarg.0
0x16483  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x16488  ldnull
0x16489  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1648e  ldarg.0
0x1648f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x16494  ldstr    aValue// "Value"
0x16499  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1649e  ldarg.0
0x1649f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x164a4  ldnull
0x164a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x164aa  ldarg.0
0x164ab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x164b0  ldc.i4.0
0x164b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x164b6  ldarg.0
0x164b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x164bc  ldc.i4.0
0x164bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x164c2  ldarg.0
0x164c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x164c8  ldc.i4.0
0x164c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x164ce  ldarg.0
0x164cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x164d4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x164d9  ldarg.0
0x164da  ldc.i4.5
0x164db  stfld    int32 <GetProperties>d__3::<>1__state
0x164e0  ldc.i4.1
0x164e1  stloc.0
0x164e2  leave.s  loc_164F6
0x164e4  ldarg.0
0x164e5  ldc.i4.m1
0x164e6  stfld    int32 <GetProperties>d__3::<>1__state
0x164eb  ldc.i4.0
0x164ec  stloc.0
0x164ed  leave.s  loc_164F6
0x164ef  ldarg.0
0x164f0  call     instance void <GetProperties>d__3::System.IDisposable.Dispose()
0x164f5  endfinally
0x164f6  ldloc.0
0x164f7  ret
```
