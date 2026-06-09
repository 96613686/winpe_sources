# <GetProperties>d__3::MoveNext_2

- ea: `0x21270`
- end: `0x215b3`
- name: `<GetProperties>d__3::MoveNext_2`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb4d0`
- `0x21270`
- `0x215e0`
- `0x21640`

## pseudocode

```c

```

## disassembly

```asm
0x21270  ldarg.0
0x21271  ldfld    int32 <GetProperties>d__3::<>1__state
0x21276  stloc.1
0x21277  ldloc.1
0x21278  switch   loc_2129A, loc_215A6, loc_21304, loc_213F0, loc_214C9, loc_2159F
0x21295  br       loc_215A6
0x2129a  ldarg.0
0x2129b  ldc.i4.m1
0x2129c  stfld    int32 <GetProperties>d__3::<>1__state
0x212a1  ldarg.0
0x212a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x212a7  brtrue.s loc_212B4
0x212a9  ldstr    aProxycontext// "proxyContext"
0x212ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x212b3  throw
0x212b4  ldarg.0
0x212b5  ldarg.0
0x212b6  ldfld    class Microsoft.SharePoint.Publishing.PublishingPageInformationCsomValueTypeConverter <GetProperties>d__3::<>4__this
0x212bb  ldarg.0
0x212bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x212c1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.PublishingPageInformationCsomValueTypeConverter::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x212c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x212cb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x212d0  ldarg.0
0x212d1  ldc.i4.1
0x212d2  stfld    int32 <GetProperties>d__3::<>1__state
0x212d7  br.s     loc_2130B
0x212d9  ldarg.0
0x212da  ldarg.0
0x212db  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x212e0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x212e5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x212ea  ldarg.0
0x212eb  ldarg.0
0x212ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x212f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x212f6  ldarg.0
0x212f7  ldc.i4.2
0x212f8  stfld    int32 <GetProperties>d__3::<>1__state
0x212fd  ldc.i4.1
0x212fe  stloc.0
0x212ff  leave    loc_215B1
0x21304  ldarg.0
0x21305  ldc.i4.1
0x21306  stfld    int32 <GetProperties>d__3::<>1__state
0x2130b  ldarg.0
0x2130c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x21311  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21316  brtrue.s loc_212D9
0x21318  ldarg.0
0x21319  call     instance void <GetProperties>d__3::<>m__Finally6()
0x2131e  ldarg.0
0x2131f  ldarg.0
0x21320  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x21325  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2132a  ldarg.0
0x2132b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x21330  ldstr    aFolder// "Folder"
0x21335  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2133a  ldarg.0
0x2133b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x21340  ldc.i4.0
0x21341  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x21346  ldarg.0
0x21347  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2134c  ldc.i4.4
0x2134d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x21352  ldarg.0
0x21353  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x21358  ldc.i4.0
0x21359  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2135e  ldarg.0
0x2135f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x21364  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x21369  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2136e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x21373  ldarg.0
0x21374  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x21379  ldc.i4.0
0x2137a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2137f  ldarg.0
0x21380  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x21385  ldc.i4.1
0x21386  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2138b  ldarg.0
0x2138c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x21391  ldnull
0x21392  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x21397  ldarg.0
0x21398  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2139d  ldstr    aFolder// "Folder"
0x213a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x213a7  ldarg.0
0x213a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x213ad  ldnull
0x213ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x213b3  ldarg.0
0x213b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x213b9  ldc.i4.0
0x213ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x213bf  ldarg.0
0x213c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x213c5  ldc.i4.0
0x213c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x213cb  ldarg.0
0x213cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x213d1  ldc.i4.0
0x213d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x213d7  ldarg.0
0x213d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x213dd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x213e2  ldarg.0
0x213e3  ldc.i4.3
0x213e4  stfld    int32 <GetProperties>d__3::<>1__state
0x213e9  ldc.i4.1
0x213ea  stloc.0
0x213eb  leave    loc_215B1
0x213f0  ldarg.0
0x213f1  ldc.i4.m1
0x213f2  stfld    int32 <GetProperties>d__3::<>1__state
0x213f7  ldarg.0
0x213f8  ldarg.0
0x213f9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x213fe  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21403  ldarg.0
0x21404  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21409  ldstr    aName// "Name"
0x2140e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x21413  ldarg.0
0x21414  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21419  ldc.i4.0
0x2141a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2141f  ldarg.0
0x21420  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21425  ldc.i4.1
0x21426  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2142b  ldarg.0
0x2142c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21431  ldc.i4.0
0x21432  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x21437  ldarg.0
0x21438  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2143d  ldtoken  [mscorlib]System.String
0x21442  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21447  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2144c  ldarg.0
0x2144d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21452  ldc.i4.0
0x21453  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x21458  ldarg.0
0x21459  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2145e  ldc.i4.1
0x2145f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x21464  ldarg.0
0x21465  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2146a  ldnull
0x2146b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x21470  ldarg.0
0x21471  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21476  ldstr    aName// "Name"
0x2147b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x21480  ldarg.0
0x21481  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21486  ldnull
0x21487  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2148c  ldarg.0
0x2148d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21492  ldc.i4.0
0x21493  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21498  ldarg.0
0x21499  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2149e  ldc.i4.0
0x2149f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x214a4  ldarg.0
0x214a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x214aa  ldc.i4.0
0x214ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x214b0  ldarg.0
0x214b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x214b6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x214bb  ldarg.0
0x214bc  ldc.i4.4
0x214bd  stfld    int32 <GetProperties>d__3::<>1__state
0x214c2  ldc.i4.1
0x214c3  stloc.0
0x214c4  leave    loc_215B1
0x214c9  ldarg.0
0x214ca  ldc.i4.m1
0x214cb  stfld    int32 <GetProperties>d__3::<>1__state
0x214d0  ldarg.0
0x214d1  ldarg.0
0x214d2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x214d7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x214dc  ldarg.0
0x214dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x214e2  ldstr    aPagelayoutlist// "PageLayoutListItem"
0x214e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x214ec  ldarg.0
0x214ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x214f2  ldc.i4.0
0x214f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x214f8  ldarg.0
0x214f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x214fe  ldc.i4.4
0x214ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x21504  ldarg.0
0x21505  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2150a  ldc.i4.0
0x2150b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x21510  ldarg.0
0x21511  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21516  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x2151b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21520  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x21525  ldarg.0
0x21526  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2152b  ldc.i4.0
0x2152c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x21531  ldarg.0
0x21532  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21537  ldc.i4.1
0x21538  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2153d  ldarg.0
0x2153e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21543  ldnull
0x21544  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x21549  ldarg.0
0x2154a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2154f  ldstr    aPagelayoutlist// "PageLayoutListItem"
0x21554  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x21559  ldarg.0
0x2155a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2155f  ldnull
0x21560  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x21565  ldarg.0
0x21566  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2156b  ldc.i4.0
0x2156c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21571  ldarg.0
0x21572  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21577  ldc.i4.0
0x21578  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2157d  ldarg.0
0x2157e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21583  ldc.i4.0
0x21584  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x21589  ldarg.0
0x2158a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2158f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x21594  ldarg.0
0x21595  ldc.i4.5
0x21596  stfld    int32 <GetProperties>d__3::<>1__state
0x2159b  ldc.i4.1
0x2159c  stloc.0
0x2159d  leave.s  loc_215B1
0x2159f  ldarg.0
0x215a0  ldc.i4.m1
0x215a1  stfld    int32 <GetProperties>d__3::<>1__state
0x215a6  ldc.i4.0
0x215a7  stloc.0
0x215a8  leave.s  loc_215B1
0x215aa  ldarg.0
0x215ab  call     instance void <GetProperties>d__3::System.IDisposable.Dispose()
0x215b0  endfinally
0x215b1  ldloc.0
0x215b2  ret
```
