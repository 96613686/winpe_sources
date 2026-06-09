# <GetProperties>d__6::MoveNext_0

- ea: `0xe0230`
- end: `0xe0819`
- name: `<GetProperties>d__6::MoveNext_0`
- size: `1513`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1c0d0`
- `0xe0230`
- `0xe0840`
- `0xe08a0`

## string_xrefs

- `0xe02fc`: `ComponentType`
- `0xe036e`: `ComponentType`
- `0xe04b3`: `Manifest`
- `0xe0520`: `Manifest`
- `0xe058c`: `ManifestType`
- `0xe05fe`: `ManifestType`

## pseudocode

```c

```

## disassembly

```asm
0xe0230  ldarg.0
0xe0231  ldfld    int32 <GetProperties>d__6::<>1__state
0xe0236  stloc.1
0xe0237  ldloc.1
0xe0238  switch   loc_E0266, loc_E080C, loc_E02D0, loc_E03C1, loc_E049A, loc_E0573, loc_E0651, loc_E072A, loc_E0805
0xe0261  br       loc_E080C
0xe0266  ldarg.0
0xe0267  ldc.i4.m1
0xe0268  stfld    int32 <GetProperties>d__6::<>1__state
0xe026d  ldarg.0
0xe026e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0xe0273  brtrue.s loc_E0280
0xe0275  ldstr    aProxycontext// "proxyContext"
0xe027a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe027f  throw
0xe0280  ldarg.0
0xe0281  ldarg.0
0xe0282  ldfld    class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultValueTypeConverter <GetProperties>d__6::<>4__this
0xe0287  ldarg.0
0xe0288  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0xe028d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultValueTypeConverter::<>n__FabricatedMethoda(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0xe0292  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0xe0297  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0xe029c  ldarg.0
0xe029d  ldc.i4.1
0xe029e  stfld    int32 <GetProperties>d__6::<>1__state
0xe02a3  br.s     loc_E02D7
0xe02a5  ldarg.0
0xe02a6  ldarg.0
0xe02a7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0xe02ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0xe02b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0xe02b6  ldarg.0
0xe02b7  ldarg.0
0xe02b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0xe02bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0xe02c2  ldarg.0
0xe02c3  ldc.i4.2
0xe02c4  stfld    int32 <GetProperties>d__6::<>1__state
0xe02c9  ldc.i4.1
0xe02ca  stloc.0
0xe02cb  leave    loc_E0817
0xe02d0  ldarg.0
0xe02d1  ldc.i4.1
0xe02d2  stfld    int32 <GetProperties>d__6::<>1__state
0xe02d7  ldarg.0
0xe02d8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0xe02dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe02e2  brtrue.s loc_E02A5
0xe02e4  ldarg.0
0xe02e5  call     instance void <GetProperties>d__6::<>m__Finally9()
0xe02ea  ldarg.0
0xe02eb  ldarg.0
0xe02ec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xe02f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe02f6  ldarg.0
0xe02f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe02fc  ldstr    aComponenttype// "ComponentType"
0xe0301  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xe0306  ldarg.0
0xe0307  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe030c  ldc.i4.0
0xe030d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xe0312  ldarg.0
0xe0313  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe0318  ldc.i4.1
0xe0319  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe031e  ldarg.0
0xe031f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe0324  ldc.i4.0
0xe0325  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xe032a  ldarg.0
0xe032b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe0330  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentType
0xe0335  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe033a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xe033f  ldarg.0
0xe0340  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe0345  ldc.i4.0
0xe0346  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xe034b  ldarg.0
0xe034c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe0351  ldc.i4.1
0xe0352  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xe0357  ldarg.0
0xe0358  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe035d  ldc.i4.0
0xe035e  box      [Microsoft.SharePoint]Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentType
0xe0363  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xe0368  ldarg.0
0xe0369  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe036e  ldstr    aComponenttype// "ComponentType"
0xe0373  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xe0378  ldarg.0
0xe0379  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe037e  ldnull
0xe037f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xe0384  ldarg.0
0xe0385  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe038a  ldc.i4.0
0xe038b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe0390  ldarg.0
0xe0391  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe0396  ldc.i4.0
0xe0397  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xe039c  ldarg.0
0xe039d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe03a2  ldc.i4.0
0xe03a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xe03a8  ldarg.0
0xe03a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0xe03ae  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0xe03b3  ldarg.0
0xe03b4  ldc.i4.3
0xe03b5  stfld    int32 <GetProperties>d__6::<>1__state
0xe03ba  ldc.i4.1
0xe03bb  stloc.0
0xe03bc  leave    loc_E0817
0xe03c1  ldarg.0
0xe03c2  ldc.i4.m1
0xe03c3  stfld    int32 <GetProperties>d__6::<>1__state
0xe03c8  ldarg.0
0xe03c9  ldarg.0
0xe03ca  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xe03cf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe03d4  ldarg.0
0xe03d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe03da  ldstr    aId_0// "Id"
0xe03df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xe03e4  ldarg.0
0xe03e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe03ea  ldc.i4.0
0xe03eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xe03f0  ldarg.0
0xe03f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe03f6  ldc.i4.1
0xe03f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe03fc  ldarg.0
0xe03fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe0402  ldc.i4.0
0xe0403  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xe0408  ldarg.0
0xe0409  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe040e  ldtoken  [mscorlib]System.String
0xe0413  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0418  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xe041d  ldarg.0
0xe041e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe0423  ldc.i4.0
0xe0424  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xe0429  ldarg.0
0xe042a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe042f  ldc.i4.1
0xe0430  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xe0435  ldarg.0
0xe0436  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe043b  ldnull
0xe043c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xe0441  ldarg.0
0xe0442  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe0447  ldstr    aId_0// "Id"
0xe044c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xe0451  ldarg.0
0xe0452  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe0457  ldnull
0xe0458  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xe045d  ldarg.0
0xe045e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe0463  ldc.i4.0
0xe0464  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe0469  ldarg.0
0xe046a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe046f  ldc.i4.0
0xe0470  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xe0475  ldarg.0
0xe0476  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe047b  ldc.i4.0
0xe047c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xe0481  ldarg.0
0xe0482  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0xe0487  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0xe048c  ldarg.0
0xe048d  ldc.i4.4
0xe048e  stfld    int32 <GetProperties>d__6::<>1__state
0xe0493  ldc.i4.1
0xe0494  stloc.0
0xe0495  leave    loc_E0817
0xe049a  ldarg.0
0xe049b  ldc.i4.m1
0xe049c  stfld    int32 <GetProperties>d__6::<>1__state
0xe04a1  ldarg.0
0xe04a2  ldarg.0
0xe04a3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xe04a8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe04ad  ldarg.0
0xe04ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe04b3  ldstr    aManifest// "Manifest"
0xe04b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xe04bd  ldarg.0
0xe04be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe04c3  ldc.i4.0
0xe04c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xe04c9  ldarg.0
0xe04ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe04cf  ldc.i4.1
0xe04d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe04d5  ldarg.0
0xe04d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe04db  ldc.i4.0
0xe04dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xe04e1  ldarg.0
0xe04e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe04e7  ldtoken  [mscorlib]System.String
0xe04ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe04f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xe04f6  ldarg.0
0xe04f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe04fc  ldc.i4.0
0xe04fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xe0502  ldarg.0
0xe0503  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe0508  ldc.i4.1
0xe0509  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xe050e  ldarg.0
0xe050f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe0514  ldnull
0xe0515  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xe051a  ldarg.0
0xe051b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe0520  ldstr    aManifest// "Manifest"
0xe0525  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xe052a  ldarg.0
0xe052b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe0530  ldnull
0xe0531  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xe0536  ldarg.0
0xe0537  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe053c  ldc.i4.0
0xe053d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe0542  ldarg.0
0xe0543  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe0548  ldc.i4.0
0xe0549  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xe054e  ldarg.0
0xe054f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe0554  ldc.i4.0
0xe0555  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xe055a  ldarg.0
0xe055b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0xe0560  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0xe0565  ldarg.0
0xe0566  ldc.i4.5
0xe0567  stfld    int32 <GetProperties>d__6::<>1__state
0xe056c  ldc.i4.1
0xe056d  stloc.0
0xe056e  leave    loc_E0817
0xe0573  ldarg.0
0xe0574  ldc.i4.m1
0xe0575  stfld    int32 <GetProperties>d__6::<>1__state
0xe057a  ldarg.0
0xe057b  ldarg.0
0xe057c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xe0581  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe0586  ldarg.0
0xe0587  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe058c  ldstr    aManifesttype// "ManifestType"
0xe0591  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xe0596  ldarg.0
0xe0597  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe059c  ldc.i4.0
0xe059d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xe05a2  ldarg.0
0xe05a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe05a8  ldc.i4.1
0xe05a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe05ae  ldarg.0
0xe05af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe05b4  ldc.i4.0
0xe05b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xe05ba  ldarg.0
0xe05bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe05c0  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.ClientSideComponent.SPClientSideManifestType
0xe05c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe05ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xe05cf  ldarg.0
0xe05d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe05d5  ldc.i4.0
0xe05d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xe05db  ldarg.0
0xe05dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe05e1  ldc.i4.1
0xe05e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xe05e7  ldarg.0
0xe05e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe05ed  ldc.i4.0
0xe05ee  box      [Microsoft.SharePoint]Microsoft.SharePoint.ClientSideComponent.SPClientSideManifestType
0xe05f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xe05f8  ldarg.0
0xe05f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0xe05fe  ldstr    aManifesttype// "ManifestType"
  ... truncated ...
```
