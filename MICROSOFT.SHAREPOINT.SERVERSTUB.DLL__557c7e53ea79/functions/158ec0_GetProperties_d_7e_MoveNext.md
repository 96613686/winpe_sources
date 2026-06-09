# <GetProperties>d__7e::MoveNext

- ea: `0x158ec0`
- end: `0x15fcad`
- name: `<GetProperties>d__7e::MoveNext`
- size: `28141`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x7b110`
- `0x158ec0`
- `0x15fcd0`
- `0x15fd30`

## string_xrefs

- `0x15d8ee`: `HasOverrideSelectCommand`
- `0x15d95b`: `HasOverrideSelectCommand`
- `0x15e098`: `OverrideSelectCommand`
- `0x15e105`: `OverrideSelectCommand`
- `0x15fafe`: `ViewPath`
- `0x15fb6b`: `ViewPath`

## pseudocode

```c

```

## disassembly

```asm
0x158ec0  ldarg.0
0x158ec1  ldfld    int32 <GetProperties>d__7e::<>1__state
0x158ec6  stloc.1
0x158ec7  ldloc.1
0x158ec8  switch   loc_1590D6, loc_15FCA0, loc_159140, loc_15922C, loc_159305, loc_1593DE, loc_1594B7, loc_159590, loc_159669, loc_159743, loc_15981D, loc_1598F7, loc_1599D1, loc_159AAB, loc_159B85, loc_159C5F, loc_159D39, loc_159E13, loc_159EED, loc_159FC7, loc_15A0A1, loc_15A17B, loc_15A255, loc_15A32F, loc_15A409, loc_15A4E3, loc_15A5BD, loc_15A697, loc_15A771, loc_15A84B, loc_15A925, loc_15A9FF, loc_15AAD9, loc_15ABB3, loc_15AC8D, loc_15AD67, loc_15AE41, loc_15AF1B, loc_15AFF5, loc_15B0CF, loc_15B1A9, loc_15B283, loc_15B35D, loc_15B437, loc_15B511, loc_15B5EB, loc_15B6C5, loc_15B79F, loc_15B879, loc_15B953, loc_15BA2D, loc_15BB07, loc_15BBE1 \
0x1590d1  br       loc_15FCA0
0x1590d6  ldarg.0
0x1590d7  ldc.i4.m1
0x1590d8  stfld    int32 <GetProperties>d__7e::<>1__state
0x1590dd  ldarg.0
0x1590de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7e::proxyContext
0x1590e3  brtrue.s loc_1590F0
0x1590e5  ldstr    aProxycontext// "proxyContext"
0x1590ea  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1590ef  throw
0x1590f0  ldarg.0
0x1590f1  ldarg.0
0x1590f2  ldfld    class Microsoft.SharePoint.ServerStub.SPRenderListDataOverrideParametersValueTypeConverter <GetProperties>d__7e::<>4__this
0x1590f7  ldarg.0
0x1590f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7e::proxyContext
0x1590fd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPRenderListDataOverrideParametersValueTypeConverter::<>n__FabricatedMethod82(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x159102  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x159107  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7e::<>7__wrap80
0x15910c  ldarg.0
0x15910d  ldc.i4.1
0x15910e  stfld    int32 <GetProperties>d__7e::<>1__state
0x159113  br.s     loc_159147
0x159115  ldarg.0
0x159116  ldarg.0
0x159117  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7e::<>7__wrap80
0x15911c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x159121  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<item>5__7f
0x159126  ldarg.0
0x159127  ldarg.0
0x159128  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<item>5__7f
0x15912d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>2__current
0x159132  ldarg.0
0x159133  ldc.i4.2
0x159134  stfld    int32 <GetProperties>d__7e::<>1__state
0x159139  ldc.i4.1
0x15913a  stloc.0
0x15913b  leave    loc_15FCAB
0x159140  ldarg.0
0x159141  ldc.i4.1
0x159142  stfld    int32 <GetProperties>d__7e::<>1__state
0x159147  ldarg.0
0x159148  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7e::<>7__wrap80
0x15914d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x159152  brtrue.s loc_159115
0x159154  ldarg.0
0x159155  call     instance void <GetProperties>d__7e::<>m__Finally81()
0x15915a  ldarg.0
0x15915b  ldarg.0
0x15915c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x159161  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x159166  ldarg.0
0x159167  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x15916c  ldstr    aCascdelwarnmes// "CascDelWarnMessage"
0x159171  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x159176  ldarg.0
0x159177  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x15917c  ldc.i4.0
0x15917d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x159182  ldarg.0
0x159183  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x159188  ldc.i4.1
0x159189  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15918e  ldarg.0
0x15918f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x159194  ldc.i4.0
0x159195  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x15919a  ldarg.0
0x15919b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x1591a0  ldtoken  [mscorlib]System.String
0x1591a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1591aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1591af  ldarg.0
0x1591b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x1591b5  ldc.i4.0
0x1591b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1591bb  ldarg.0
0x1591bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x1591c1  ldc.i4.1
0x1591c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1591c7  ldarg.0
0x1591c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x1591cd  ldnull
0x1591ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1591d3  ldarg.0
0x1591d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x1591d9  ldstr    aCascdelwarnmes// "CascDelWarnMessage"
0x1591de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1591e3  ldarg.0
0x1591e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x1591e9  ldnull
0x1591ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1591ef  ldarg.0
0x1591f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x1591f5  ldc.i4.0
0x1591f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1591fb  ldarg.0
0x1591fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x159201  ldc.i4.0
0x159202  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x159207  ldarg.0
0x159208  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x15920d  ldc.i4.1
0x15920e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x159213  ldarg.0
0x159214  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal0
0x159219  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>2__current
0x15921e  ldarg.0
0x15921f  ldc.i4.3
0x159220  stfld    int32 <GetProperties>d__7e::<>1__state
0x159225  ldc.i4.1
0x159226  stloc.0
0x159227  leave    loc_15FCAB
0x15922c  ldarg.0
0x15922d  ldc.i4.m1
0x15922e  stfld    int32 <GetProperties>d__7e::<>1__state
0x159233  ldarg.0
0x159234  ldarg.0
0x159235  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15923a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x15923f  ldarg.0
0x159240  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x159245  ldstr    aCustomaction// "CustomAction"
0x15924a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x15924f  ldarg.0
0x159250  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x159255  ldc.i4.0
0x159256  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x15925b  ldarg.0
0x15925c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x159261  ldc.i4.1
0x159262  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x159267  ldarg.0
0x159268  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x15926d  ldc.i4.0
0x15926e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x159273  ldarg.0
0x159274  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x159279  ldtoken  [mscorlib]System.String
0x15927e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159283  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x159288  ldarg.0
0x159289  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x15928e  ldc.i4.0
0x15928f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x159294  ldarg.0
0x159295  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x15929a  ldc.i4.1
0x15929b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1592a0  ldarg.0
0x1592a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x1592a6  ldnull
0x1592a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1592ac  ldarg.0
0x1592ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x1592b2  ldstr    aCustomaction// "CustomAction"
0x1592b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1592bc  ldarg.0
0x1592bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x1592c2  ldnull
0x1592c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1592c8  ldarg.0
0x1592c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x1592ce  ldc.i4.0
0x1592cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1592d4  ldarg.0
0x1592d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x1592da  ldc.i4.0
0x1592db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1592e0  ldarg.0
0x1592e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x1592e6  ldc.i4.1
0x1592e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1592ec  ldarg.0
0x1592ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal1
0x1592f2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>2__current
0x1592f7  ldarg.0
0x1592f8  ldc.i4.4
0x1592f9  stfld    int32 <GetProperties>d__7e::<>1__state
0x1592fe  ldc.i4.1
0x1592ff  stloc.0
0x159300  leave    loc_15FCAB
0x159305  ldarg.0
0x159306  ldc.i4.m1
0x159307  stfld    int32 <GetProperties>d__7e::<>1__state
0x15930c  ldarg.0
0x15930d  ldarg.0
0x15930e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x159313  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x159318  ldarg.0
0x159319  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x15931e  ldstr    aDrilldown// "DrillDown"
0x159323  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x159328  ldarg.0
0x159329  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x15932e  ldc.i4.0
0x15932f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x159334  ldarg.0
0x159335  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x15933a  ldc.i4.1
0x15933b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x159340  ldarg.0
0x159341  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x159346  ldc.i4.0
0x159347  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x15934c  ldarg.0
0x15934d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x159352  ldtoken  [mscorlib]System.String
0x159357  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15935c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x159361  ldarg.0
0x159362  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x159367  ldc.i4.0
0x159368  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x15936d  ldarg.0
0x15936e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x159373  ldc.i4.1
0x159374  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x159379  ldarg.0
0x15937a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x15937f  ldnull
0x159380  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x159385  ldarg.0
0x159386  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x15938b  ldstr    aDrilldown// "DrillDown"
0x159390  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x159395  ldarg.0
0x159396  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x15939b  ldnull
0x15939c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1593a1  ldarg.0
0x1593a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x1593a7  ldc.i4.0
0x1593a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1593ad  ldarg.0
0x1593ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x1593b3  ldc.i4.0
0x1593b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1593b9  ldarg.0
0x1593ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x1593bf  ldc.i4.1
0x1593c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1593c5  ldarg.0
0x1593c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal2
0x1593cb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>2__current
0x1593d0  ldarg.0
0x1593d1  ldc.i4.5
0x1593d2  stfld    int32 <GetProperties>d__7e::<>1__state
0x1593d7  ldc.i4.1
0x1593d8  stloc.0
0x1593d9  leave    loc_15FCAB
0x1593de  ldarg.0
0x1593df  ldc.i4.m1
0x1593e0  stfld    int32 <GetProperties>d__7e::<>1__state
0x1593e5  ldarg.0
0x1593e6  ldarg.0
0x1593e7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1593ec  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x1593f1  ldarg.0
0x1593f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x1593f7  ldstr    aField// "Field"
0x1593fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x159401  ldarg.0
0x159402  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x159407  ldc.i4.0
0x159408  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x15940d  ldarg.0
0x15940e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x159413  ldc.i4.1
0x159414  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x159419  ldarg.0
0x15941a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x15941f  ldc.i4.0
0x159420  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x159425  ldarg.0
0x159426  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x15942b  ldtoken  [mscorlib]System.String
0x159430  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159435  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x15943a  ldarg.0
0x15943b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x159440  ldc.i4.0
0x159441  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x159446  ldarg.0
0x159447  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x15944c  ldc.i4.1
0x15944d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x159452  ldarg.0
0x159453  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x159458  ldnull
0x159459  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15945e  ldarg.0
0x15945f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7e::<>g__initLocal3
0x159464  ldstr    aField// "Field"
0x159469  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15946e  ldarg.0
  ... truncated ...
```
