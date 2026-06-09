# <GetProperties>d__6::MoveNext

- ea: `0x25640`
- end: `0x25c27`
- name: `<GetProperties>d__6::MoveNext`
- size: `1511`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0xe3b0`
- `0x25640`
- `0x25c50`
- `0x25cb0`

## string_xrefs

- `0x258be`: `CanvasJson1`
- `0x2592b`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0x25640  ldarg.0
0x25641  ldfld    int32 <GetProperties>d__6::<>1__state
0x25646  stloc.1
0x25647  ldloc.1
0x25648  switch   loc_25676, loc_25C1A, loc_256E0, loc_257CC, loc_258A5, loc_2597E, loc_25A57, loc_25B3D, loc_25C13
0x25671  br       loc_25C1A
0x25676  ldarg.0
0x25677  ldc.i4.m1
0x25678  stfld    int32 <GetProperties>d__6::<>1__state
0x2567d  ldarg.0
0x2567e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0x25683  brtrue.s loc_25690
0x25685  ldstr    aProxycontext// "proxyContext"
0x2568a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2568f  throw
0x25690  ldarg.0
0x25691  ldarg.0
0x25692  ldfld    class Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter <GetProperties>d__6::<>4__this
0x25697  ldarg.0
0x25698  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0x2569d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::<>n__FabricatedMethoda(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x256a2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x256a7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x256ac  ldarg.0
0x256ad  ldc.i4.1
0x256ae  stfld    int32 <GetProperties>d__6::<>1__state
0x256b3  br.s     loc_256E7
0x256b5  ldarg.0
0x256b6  ldarg.0
0x256b7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x256bc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x256c1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0x256c6  ldarg.0
0x256c7  ldarg.0
0x256c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0x256cd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x256d2  ldarg.0
0x256d3  ldc.i4.2
0x256d4  stfld    int32 <GetProperties>d__6::<>1__state
0x256d9  ldc.i4.1
0x256da  stloc.0
0x256db  leave    loc_25C25
0x256e0  ldarg.0
0x256e1  ldc.i4.1
0x256e2  stfld    int32 <GetProperties>d__6::<>1__state
0x256e7  ldarg.0
0x256e8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x256ed  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x256f2  brtrue.s loc_256B5
0x256f4  ldarg.0
0x256f5  call     instance void <GetProperties>d__6::<>m__Finally9()
0x256fa  ldarg.0
0x256fb  ldarg.0
0x256fc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x25701  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25706  ldarg.0
0x25707  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2570c  ldstr    aBannerimageurl// "BannerImageUrl"
0x25711  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x25716  ldarg.0
0x25717  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2571c  ldc.i4.0
0x2571d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x25722  ldarg.0
0x25723  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25728  ldc.i4.1
0x25729  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2572e  ldarg.0
0x2572f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25734  ldc.i4.0
0x25735  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2573a  ldarg.0
0x2573b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25740  ldtoken  [mscorlib]System.String
0x25745  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2574a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2574f  ldarg.0
0x25750  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25755  ldc.i4.0
0x25756  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2575b  ldarg.0
0x2575c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25761  ldc.i4.1
0x25762  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x25767  ldarg.0
0x25768  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x2576d  ldnull
0x2576e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x25773  ldarg.0
0x25774  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25779  ldstr    aBannerimageurl// "BannerImageUrl"
0x2577e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x25783  ldarg.0
0x25784  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25789  ldnull
0x2578a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2578f  ldarg.0
0x25790  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x25795  ldc.i4.0
0x25796  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2579b  ldarg.0
0x2579c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x257a1  ldc.i4.1
0x257a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x257a7  ldarg.0
0x257a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x257ad  ldc.i4.0
0x257ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x257b3  ldarg.0
0x257b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x257b9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x257be  ldarg.0
0x257bf  ldc.i4.3
0x257c0  stfld    int32 <GetProperties>d__6::<>1__state
0x257c5  ldc.i4.1
0x257c6  stloc.0
0x257c7  leave    loc_25C25
0x257cc  ldarg.0
0x257cd  ldc.i4.m1
0x257ce  stfld    int32 <GetProperties>d__6::<>1__state
0x257d3  ldarg.0
0x257d4  ldarg.0
0x257d5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x257da  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x257df  ldarg.0
0x257e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x257e5  ldstr    aCanvascontent1// "CanvasContent1"
0x257ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x257ef  ldarg.0
0x257f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x257f5  ldc.i4.0
0x257f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x257fb  ldarg.0
0x257fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x25801  ldc.i4.1
0x25802  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x25807  ldarg.0
0x25808  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2580d  ldc.i4.0
0x2580e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x25813  ldarg.0
0x25814  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x25819  ldtoken  [mscorlib]System.String
0x2581e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25823  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x25828  ldarg.0
0x25829  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2582e  ldc.i4.0
0x2582f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x25834  ldarg.0
0x25835  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2583a  ldc.i4.1
0x2583b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x25840  ldarg.0
0x25841  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x25846  ldnull
0x25847  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2584c  ldarg.0
0x2584d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x25852  ldstr    aCanvascontent1// "CanvasContent1"
0x25857  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2585c  ldarg.0
0x2585d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x25862  ldnull
0x25863  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x25868  ldarg.0
0x25869  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2586e  ldc.i4.0
0x2586f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x25874  ldarg.0
0x25875  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x2587a  ldc.i4.1
0x2587b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x25880  ldarg.0
0x25881  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x25886  ldc.i4.0
0x25887  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2588c  ldarg.0
0x2588d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x25892  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x25897  ldarg.0
0x25898  ldc.i4.4
0x25899  stfld    int32 <GetProperties>d__6::<>1__state
0x2589e  ldc.i4.1
0x2589f  stloc.0
0x258a0  leave    loc_25C25
0x258a5  ldarg.0
0x258a6  ldc.i4.m1
0x258a7  stfld    int32 <GetProperties>d__6::<>1__state
0x258ac  ldarg.0
0x258ad  ldarg.0
0x258ae  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x258b3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x258b8  ldarg.0
0x258b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x258be  ldstr    aCanvasjson1// "CanvasJson1"
0x258c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x258c8  ldarg.0
0x258c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x258ce  ldc.i4.0
0x258cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x258d4  ldarg.0
0x258d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x258da  ldc.i4.1
0x258db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x258e0  ldarg.0
0x258e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x258e6  ldc.i4.1
0x258e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x258ec  ldarg.0
0x258ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x258f2  ldtoken  [mscorlib]System.String
0x258f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x258fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x25901  ldarg.0
0x25902  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x25907  ldc.i4.0
0x25908  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2590d  ldarg.0
0x2590e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x25913  ldc.i4.1
0x25914  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x25919  ldarg.0
0x2591a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2591f  ldnull
0x25920  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x25925  ldarg.0
0x25926  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2592b  ldstr    aCanvasjson1// "CanvasJson1"
0x25930  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x25935  ldarg.0
0x25936  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2593b  ldnull
0x2593c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x25941  ldarg.0
0x25942  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x25947  ldc.i4.0
0x25948  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2594d  ldarg.0
0x2594e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x25953  ldc.i4.1
0x25954  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x25959  ldarg.0
0x2595a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2595f  ldc.i4.0
0x25960  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x25965  ldarg.0
0x25966  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x2596b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x25970  ldarg.0
0x25971  ldc.i4.5
0x25972  stfld    int32 <GetProperties>d__6::<>1__state
0x25977  ldc.i4.1
0x25978  stloc.0
0x25979  leave    loc_25C25
0x2597e  ldarg.0
0x2597f  ldc.i4.m1
0x25980  stfld    int32 <GetProperties>d__6::<>1__state
0x25985  ldarg.0
0x25986  ldarg.0
0x25987  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2598c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x25991  ldarg.0
0x25992  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x25997  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x2599c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x259a1  ldarg.0
0x259a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x259a7  ldc.i4.0
0x259a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x259ad  ldarg.0
0x259ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x259b3  ldc.i4.1
0x259b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x259b9  ldarg.0
0x259ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x259bf  ldc.i4.0
0x259c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x259c5  ldarg.0
0x259c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x259cb  ldtoken  [mscorlib]System.String
0x259d0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x259d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x259da  ldarg.0
0x259db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x259e0  ldc.i4.0
0x259e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x259e6  ldarg.0
0x259e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x259ec  ldc.i4.1
0x259ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x259f2  ldarg.0
0x259f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x259f8  ldnull
0x259f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x259fe  ldarg.0
0x259ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x25a04  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x25a09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x25a0e  ldarg.0
  ... truncated ...
```
