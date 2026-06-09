# <GetProperties>d__1a::MoveNext

- ea: `0x26150`
- end: `0x278db`
- name: `<GetProperties>d__1a::MoveNext`
- size: `6027`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xfc50`
- `0x26150`
- `0x27900`
- `0x27960`

## string_xrefs

- `0x2641e`: `CommentsDisabled`
- `0x26490`: `CommentsDisabled`
- `0x265d5`: `CreatedBy`
- `0x26642`: `CreatedBy`
- `0x26cbf`: `IsWebWelcomePage`
- `0x26d31`: `IsWebWelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0x26150  ldarg.0
0x26151  ldfld    int32 <GetProperties>d__1a::<>1__state
0x26156  stloc.1
0x26157  ldloc.1
0x26158  switch   loc_261D6, loc_278CE, loc_26240, loc_2632C, loc_26405, loc_264E3, loc_265BC, loc_26695, loc_2676E, loc_2684D, loc_26927, loc_26A0E, loc_26AE8, loc_26BC7, loc_26CA6, loc_26D85, loc_26E5F, loc_26F46, loc_2702E, loc_27108, loc_271E2, loc_272BC, loc_2739B, loc_2747A, loc_27554, loc_2763C, loc_27716, loc_277F0, loc_278C7
0x261d1  br       loc_278CE
0x261d6  ldarg.0
0x261d7  ldc.i4.m1
0x261d8  stfld    int32 <GetProperties>d__1a::<>1__state
0x261dd  ldarg.0
0x261de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1a::proxyContext
0x261e3  brtrue.s loc_261F0
0x261e5  ldstr    aProxycontext// "proxyContext"
0x261ea  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x261ef  throw
0x261f0  ldarg.0
0x261f1  ldarg.0
0x261f2  ldfld    class Microsoft.SharePoint.Publishing.SitePageMetadataServerStub <GetProperties>d__1a::<>4__this
0x261f7  ldarg.0
0x261f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1a::proxyContext
0x261fd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::<>n__FabricatedMethod1e(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x26202  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x26207  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1a::<>7__wrap1c
0x2620c  ldarg.0
0x2620d  ldc.i4.1
0x2620e  stfld    int32 <GetProperties>d__1a::<>1__state
0x26213  br.s     loc_26247
0x26215  ldarg.0
0x26216  ldarg.0
0x26217  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1a::<>7__wrap1c
0x2621c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x26221  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<item>5__1b
0x26226  ldarg.0
0x26227  ldarg.0
0x26228  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<item>5__1b
0x2622d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x26232  ldarg.0
0x26233  ldc.i4.2
0x26234  stfld    int32 <GetProperties>d__1a::<>1__state
0x26239  ldc.i4.1
0x2623a  stloc.0
0x2623b  leave    loc_278D9
0x26240  ldarg.0
0x26241  ldc.i4.1
0x26242  stfld    int32 <GetProperties>d__1a::<>1__state
0x26247  ldarg.0
0x26248  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1a::<>7__wrap1c
0x2624d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26252  brtrue.s loc_26215
0x26254  ldarg.0
0x26255  call     instance void <GetProperties>d__1a::<>m__Finally1d()
0x2625a  ldarg.0
0x2625b  ldarg.0
0x2625c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x26261  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x26266  ldarg.0
0x26267  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x2626c  ldstr    aAbsoluteurl// "AbsoluteUrl"
0x26271  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x26276  ldarg.0
0x26277  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x2627c  ldc.i4.0
0x2627d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x26282  ldarg.0
0x26283  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x26288  ldc.i4.1
0x26289  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2628e  ldarg.0
0x2628f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x26294  ldc.i4.0
0x26295  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2629a  ldarg.0
0x2629b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x262a0  ldtoken  [mscorlib]System.String
0x262a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x262aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x262af  ldarg.0
0x262b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x262b5  ldc.i4.1
0x262b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x262bb  ldarg.0
0x262bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x262c1  ldc.i4.1
0x262c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x262c7  ldarg.0
0x262c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x262cd  ldnull
0x262ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x262d3  ldarg.0
0x262d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x262d9  ldstr    aAbsoluteurl// "AbsoluteUrl"
0x262de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x262e3  ldarg.0
0x262e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x262e9  ldnull
0x262ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x262ef  ldarg.0
0x262f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x262f5  ldc.i4.0
0x262f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x262fb  ldarg.0
0x262fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x26301  ldc.i4.1
0x26302  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x26307  ldarg.0
0x26308  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x2630d  ldc.i4.0
0x2630e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x26313  ldarg.0
0x26314  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal0
0x26319  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x2631e  ldarg.0
0x2631f  ldc.i4.3
0x26320  stfld    int32 <GetProperties>d__1a::<>1__state
0x26325  ldc.i4.1
0x26326  stloc.0
0x26327  leave    loc_278D9
0x2632c  ldarg.0
0x2632d  ldc.i4.m1
0x2632e  stfld    int32 <GetProperties>d__1a::<>1__state
0x26333  ldarg.0
0x26334  ldarg.0
0x26335  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2633a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x2633f  ldarg.0
0x26340  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x26345  ldstr    aBannerimageurl// "BannerImageUrl"
0x2634a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2634f  ldarg.0
0x26350  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x26355  ldc.i4.0
0x26356  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2635b  ldarg.0
0x2635c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x26361  ldc.i4.1
0x26362  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x26367  ldarg.0
0x26368  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x2636d  ldc.i4.0
0x2636e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x26373  ldarg.0
0x26374  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x26379  ldtoken  [mscorlib]System.String
0x2637e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x26383  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x26388  ldarg.0
0x26389  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x2638e  ldc.i4.0
0x2638f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x26394  ldarg.0
0x26395  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x2639a  ldc.i4.1
0x2639b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x263a0  ldarg.0
0x263a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x263a6  ldnull
0x263a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x263ac  ldarg.0
0x263ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x263b2  ldstr    aBannerimageurl// "BannerImageUrl"
0x263b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x263bc  ldarg.0
0x263bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x263c2  ldnull
0x263c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x263c8  ldarg.0
0x263c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x263ce  ldc.i4.0
0x263cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x263d4  ldarg.0
0x263d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x263da  ldc.i4.1
0x263db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x263e0  ldarg.0
0x263e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x263e6  ldc.i4.0
0x263e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x263ec  ldarg.0
0x263ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal1
0x263f2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x263f7  ldarg.0
0x263f8  ldc.i4.4
0x263f9  stfld    int32 <GetProperties>d__1a::<>1__state
0x263fe  ldc.i4.1
0x263ff  stloc.0
0x26400  leave    loc_278D9
0x26405  ldarg.0
0x26406  ldc.i4.m1
0x26407  stfld    int32 <GetProperties>d__1a::<>1__state
0x2640c  ldarg.0
0x2640d  ldarg.0
0x2640e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x26413  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x26418  ldarg.0
0x26419  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x2641e  ldstr    aCommentsdisabl// "CommentsDisabled"
0x26423  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x26428  ldarg.0
0x26429  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x2642e  ldc.i4.0
0x2642f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x26434  ldarg.0
0x26435  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x2643a  ldc.i4.1
0x2643b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x26440  ldarg.0
0x26441  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x26446  ldc.i4.1
0x26447  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2644c  ldarg.0
0x2644d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x26452  ldtoken  [mscorlib]System.Boolean
0x26457  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2645c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x26461  ldarg.0
0x26462  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x26467  ldc.i4.1
0x26468  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2646d  ldarg.0
0x2646e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x26473  ldc.i4.1
0x26474  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x26479  ldarg.0
0x2647a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x2647f  ldc.i4.0
0x26480  box      [mscorlib]System.Boolean
0x26485  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2648a  ldarg.0
0x2648b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x26490  ldstr    aCommentsdisabl// "CommentsDisabled"
0x26495  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2649a  ldarg.0
0x2649b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x264a0  ldnull
0x264a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x264a6  ldarg.0
0x264a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x264ac  ldc.i4.0
0x264ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x264b2  ldarg.0
0x264b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x264b8  ldc.i4.1
0x264b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x264be  ldarg.0
0x264bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x264c4  ldc.i4.0
0x264c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x264ca  ldarg.0
0x264cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal2
0x264d0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x264d5  ldarg.0
0x264d6  ldc.i4.5
0x264d7  stfld    int32 <GetProperties>d__1a::<>1__state
0x264dc  ldc.i4.1
0x264dd  stloc.0
0x264de  leave    loc_278D9
0x264e3  ldarg.0
0x264e4  ldc.i4.m1
0x264e5  stfld    int32 <GetProperties>d__1a::<>1__state
0x264ea  ldarg.0
0x264eb  ldarg.0
0x264ec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x264f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x264f6  ldarg.0
0x264f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x264fc  ldstr    aContenttypeid// "ContentTypeId"
0x26501  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x26506  ldarg.0
0x26507  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x2650c  ldc.i4.0
0x2650d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x26512  ldarg.0
0x26513  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x26518  ldc.i4.1
0x26519  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2651e  ldarg.0
0x2651f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x26524  ldc.i4.0
0x26525  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2652a  ldarg.0
0x2652b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x26530  ldtoken  [mscorlib]System.String
0x26535  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2653a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2653f  ldarg.0
0x26540  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x26545  ldc.i4.0
0x26546  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2654b  ldarg.0
0x2654c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x26551  ldc.i4.1
0x26552  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x26557  ldarg.0
0x26558  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x2655d  ldnull
0x2655e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x26563  ldarg.0
0x26564  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal3
0x26569  ldstr    aContenttypeid// "ContentTypeId"
0x2656e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
