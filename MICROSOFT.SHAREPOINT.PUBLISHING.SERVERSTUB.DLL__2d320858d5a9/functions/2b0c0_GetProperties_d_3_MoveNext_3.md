# <GetProperties>d__3::MoveNext_3

- ea: `0x2b0c0`
- end: `0x2b408`
- name: `<GetProperties>d__3::MoveNext_3`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x12580`
- `0x2b0c0`
- `0x2b430`
- `0x2b490`

## pseudocode

```c

```

## disassembly

```asm
0x2b0c0  ldarg.0
0x2b0c1  ldfld    int32 <GetProperties>d__3::<>1__state
0x2b0c6  stloc.1
0x2b0c7  ldloc.1
0x2b0c8  switch   loc_2B0EA, loc_2B3FB, loc_2B154, loc_2B240, loc_2B31E, loc_2B3F4
0x2b0e5  br       loc_2B3FB
0x2b0ea  ldarg.0
0x2b0eb  ldc.i4.m1
0x2b0ec  stfld    int32 <GetProperties>d__3::<>1__state
0x2b0f1  ldarg.0
0x2b0f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x2b0f7  brtrue.s loc_2B104
0x2b0f9  ldstr    aProxycontext// "proxyContext"
0x2b0fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2b103  throw
0x2b104  ldarg.0
0x2b105  ldarg.0
0x2b106  ldfld    class Microsoft.SharePoint.Publishing.TextValueWithLanguageValueTypeConverter <GetProperties>d__3::<>4__this
0x2b10b  ldarg.0
0x2b10c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x2b111  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.TextValueWithLanguageValueTypeConverter::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x2b116  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x2b11b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x2b120  ldarg.0
0x2b121  ldc.i4.1
0x2b122  stfld    int32 <GetProperties>d__3::<>1__state
0x2b127  br.s     loc_2B15B
0x2b129  ldarg.0
0x2b12a  ldarg.0
0x2b12b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x2b130  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x2b135  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x2b13a  ldarg.0
0x2b13b  ldarg.0
0x2b13c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x2b141  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x2b146  ldarg.0
0x2b147  ldc.i4.2
0x2b148  stfld    int32 <GetProperties>d__3::<>1__state
0x2b14d  ldc.i4.1
0x2b14e  stloc.0
0x2b14f  leave    loc_2B406
0x2b154  ldarg.0
0x2b155  ldc.i4.1
0x2b156  stfld    int32 <GetProperties>d__3::<>1__state
0x2b15b  ldarg.0
0x2b15c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x2b161  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b166  brtrue.s loc_2B129
0x2b168  ldarg.0
0x2b169  call     instance void <GetProperties>d__3::<>m__Finally6()
0x2b16e  ldarg.0
0x2b16f  ldarg.0
0x2b170  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2b175  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b17a  ldarg.0
0x2b17b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b180  ldstr    aColorseed// "ColorSeed"
0x2b185  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2b18a  ldarg.0
0x2b18b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b190  ldc.i4.0
0x2b191  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2b196  ldarg.0
0x2b197  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b19c  ldc.i4.1
0x2b19d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2b1a2  ldarg.0
0x2b1a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b1a8  ldc.i4.0
0x2b1a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2b1ae  ldarg.0
0x2b1af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b1b4  ldtoken  [mscorlib]System.String
0x2b1b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b1be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2b1c3  ldarg.0
0x2b1c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b1c9  ldc.i4.0
0x2b1ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2b1cf  ldarg.0
0x2b1d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b1d5  ldc.i4.1
0x2b1d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2b1db  ldarg.0
0x2b1dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b1e1  ldnull
0x2b1e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2b1e7  ldarg.0
0x2b1e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b1ed  ldstr    aColorseed// "ColorSeed"
0x2b1f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2b1f7  ldarg.0
0x2b1f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b1fd  ldnull
0x2b1fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2b203  ldarg.0
0x2b204  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b209  ldc.i4.0
0x2b20a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2b20f  ldarg.0
0x2b210  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b215  ldc.i4.0
0x2b216  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2b21b  ldarg.0
0x2b21c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b221  ldc.i4.0
0x2b222  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2b227  ldarg.0
0x2b228  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x2b22d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x2b232  ldarg.0
0x2b233  ldc.i4.3
0x2b234  stfld    int32 <GetProperties>d__3::<>1__state
0x2b239  ldc.i4.1
0x2b23a  stloc.0
0x2b23b  leave    loc_2B406
0x2b240  ldarg.0
0x2b241  ldc.i4.m1
0x2b242  stfld    int32 <GetProperties>d__3::<>1__state
0x2b247  ldarg.0
0x2b248  ldarg.0
0x2b249  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2b24e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b253  ldarg.0
0x2b254  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b259  ldstr    aLcid// "Lcid"
0x2b25e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2b263  ldarg.0
0x2b264  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b269  ldc.i4.0
0x2b26a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2b26f  ldarg.0
0x2b270  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b275  ldc.i4.1
0x2b276  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2b27b  ldarg.0
0x2b27c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b281  ldc.i4.0
0x2b282  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2b287  ldarg.0
0x2b288  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b28d  ldtoken  [mscorlib]System.Int32
0x2b292  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b297  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2b29c  ldarg.0
0x2b29d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2a2  ldc.i4.0
0x2b2a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2b2a8  ldarg.0
0x2b2a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2ae  ldc.i4.1
0x2b2af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2b2b4  ldarg.0
0x2b2b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2ba  ldc.i4.0
0x2b2bb  box      [mscorlib]System.Int32
0x2b2c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2b2c5  ldarg.0
0x2b2c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2cb  ldstr    aLcid// "Lcid"
0x2b2d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2b2d5  ldarg.0
0x2b2d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2db  ldnull
0x2b2dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2b2e1  ldarg.0
0x2b2e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2e7  ldc.i4.0
0x2b2e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2b2ed  ldarg.0
0x2b2ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2f3  ldc.i4.0
0x2b2f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2b2f9  ldarg.0
0x2b2fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b2ff  ldc.i4.0
0x2b300  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2b305  ldarg.0
0x2b306  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2b30b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x2b310  ldarg.0
0x2b311  ldc.i4.4
0x2b312  stfld    int32 <GetProperties>d__3::<>1__state
0x2b317  ldc.i4.1
0x2b318  stloc.0
0x2b319  leave    loc_2B406
0x2b31e  ldarg.0
0x2b31f  ldc.i4.m1
0x2b320  stfld    int32 <GetProperties>d__3::<>1__state
0x2b325  ldarg.0
0x2b326  ldarg.0
0x2b327  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2b32c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b331  ldarg.0
0x2b332  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b337  ldstr    aText// "Text"
0x2b33c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2b341  ldarg.0
0x2b342  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b347  ldc.i4.0
0x2b348  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2b34d  ldarg.0
0x2b34e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b353  ldc.i4.1
0x2b354  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2b359  ldarg.0
0x2b35a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b35f  ldc.i4.0
0x2b360  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2b365  ldarg.0
0x2b366  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b36b  ldtoken  [mscorlib]System.String
0x2b370  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b375  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2b37a  ldarg.0
0x2b37b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b380  ldc.i4.0
0x2b381  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2b386  ldarg.0
0x2b387  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b38c  ldc.i4.1
0x2b38d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2b392  ldarg.0
0x2b393  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b398  ldnull
0x2b399  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2b39e  ldarg.0
0x2b39f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b3a4  ldstr    aText// "Text"
0x2b3a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2b3ae  ldarg.0
0x2b3af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b3b4  ldnull
0x2b3b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2b3ba  ldarg.0
0x2b3bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b3c0  ldc.i4.0
0x2b3c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2b3c6  ldarg.0
0x2b3c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b3cc  ldc.i4.0
0x2b3cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2b3d2  ldarg.0
0x2b3d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b3d8  ldc.i4.0
0x2b3d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2b3de  ldarg.0
0x2b3df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2b3e4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x2b3e9  ldarg.0
0x2b3ea  ldc.i4.5
0x2b3eb  stfld    int32 <GetProperties>d__3::<>1__state
0x2b3f0  ldc.i4.1
0x2b3f1  stloc.0
0x2b3f2  leave.s  loc_2B406
0x2b3f4  ldarg.0
0x2b3f5  ldc.i4.m1
0x2b3f6  stfld    int32 <GetProperties>d__3::<>1__state
0x2b3fb  ldc.i4.0
0x2b3fc  stloc.0
0x2b3fd  leave.s  loc_2B406
0x2b3ff  ldarg.0
0x2b400  call     instance void <GetProperties>d__3::System.IDisposable.Dispose()
0x2b405  endfinally
0x2b406  ldloc.0
0x2b407  ret
```
