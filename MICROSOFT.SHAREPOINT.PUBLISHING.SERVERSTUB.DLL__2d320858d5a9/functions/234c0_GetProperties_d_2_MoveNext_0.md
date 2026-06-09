# <GetProperties>d__2::MoveNext_0

- ea: `0x234c0`
- end: `0x23726`
- name: `<GetProperties>d__2::MoveNext_0`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xcc00`
- `0x234c0`
- `0x23750`
- `0x237b0`

## pseudocode

```c

```

## disassembly

```asm
0x234c0  ldarg.0
0x234c1  ldfld    int32 <GetProperties>d__2::<>1__state
0x234c6  stloc.1
0x234c7  ldloc.1
0x234c8  switch   loc_234E6, loc_23719, loc_23550, loc_2363C, loc_23712
0x234e1  br       loc_23719
0x234e6  ldarg.0
0x234e7  ldc.i4.m1
0x234e8  stfld    int32 <GetProperties>d__2::<>1__state
0x234ed  ldarg.0
0x234ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2::proxyContext
0x234f3  brtrue.s loc_23500
0x234f5  ldstr    aProxycontext// "proxyContext"
0x234fa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x234ff  throw
0x23500  ldarg.0
0x23501  ldarg.0
0x23502  ldfld    class Microsoft.SharePoint.Publishing.SharePagePreviewByEmailFieldsDataValueTypeConverter <GetProperties>d__2::<>4__this
0x23507  ldarg.0
0x23508  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2::proxyContext
0x2350d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SharePagePreviewByEmailFieldsDataValueTypeConverter::<>n__FabricatedMethod6(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x23512  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x23517  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x2351c  ldarg.0
0x2351d  ldc.i4.1
0x2351e  stfld    int32 <GetProperties>d__2::<>1__state
0x23523  br.s     loc_23557
0x23525  ldarg.0
0x23526  ldarg.0
0x23527  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x2352c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x23531  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<item>5__3
0x23536  ldarg.0
0x23537  ldarg.0
0x23538  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<item>5__3
0x2353d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x23542  ldarg.0
0x23543  ldc.i4.2
0x23544  stfld    int32 <GetProperties>d__2::<>1__state
0x23549  ldc.i4.1
0x2354a  stloc.0
0x2354b  leave    loc_23724
0x23550  ldarg.0
0x23551  ldc.i4.1
0x23552  stfld    int32 <GetProperties>d__2::<>1__state
0x23557  ldarg.0
0x23558  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2::<>7__wrap4
0x2355d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23562  brtrue.s loc_23525
0x23564  ldarg.0
0x23565  call     instance void <GetProperties>d__2::<>m__Finally5()
0x2356a  ldarg.0
0x2356b  ldarg.0
0x2356c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x23571  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x23576  ldarg.0
0x23577  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x2357c  ldstr    aMessage// "message"
0x23581  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x23586  ldarg.0
0x23587  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x2358c  ldc.i4.0
0x2358d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x23592  ldarg.0
0x23593  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x23598  ldc.i4.1
0x23599  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2359e  ldarg.0
0x2359f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x235a4  ldc.i4.0
0x235a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x235aa  ldarg.0
0x235ab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x235b0  ldtoken  [mscorlib]System.String
0x235b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x235ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x235bf  ldarg.0
0x235c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x235c5  ldc.i4.0
0x235c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x235cb  ldarg.0
0x235cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x235d1  ldc.i4.1
0x235d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x235d7  ldarg.0
0x235d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x235dd  ldnull
0x235de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x235e3  ldarg.0
0x235e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x235e9  ldstr    aMessage_0// "Message"
0x235ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x235f3  ldarg.0
0x235f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x235f9  ldnull
0x235fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x235ff  ldarg.0
0x23600  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x23605  ldc.i4.0
0x23606  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2360b  ldarg.0
0x2360c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x23611  ldc.i4.0
0x23612  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x23617  ldarg.0
0x23618  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x2361d  ldc.i4.0
0x2361e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x23623  ldarg.0
0x23624  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal0
0x23629  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x2362e  ldarg.0
0x2362f  ldc.i4.3
0x23630  stfld    int32 <GetProperties>d__2::<>1__state
0x23635  ldc.i4.1
0x23636  stloc.0
0x23637  leave    loc_23724
0x2363c  ldarg.0
0x2363d  ldc.i4.m1
0x2363e  stfld    int32 <GetProperties>d__2::<>1__state
0x23643  ldarg.0
0x23644  ldarg.0
0x23645  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2364a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2364f  ldarg.0
0x23650  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x23655  ldstr    aRecipientemail// "recipientEmails"
0x2365a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2365f  ldarg.0
0x23660  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x23665  ldc.i4.0
0x23666  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2366b  ldarg.0
0x2366c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x23671  ldc.i4.3
0x23672  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x23677  ldarg.0
0x23678  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2367d  ldc.i4.0
0x2367e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x23683  ldarg.0
0x23684  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x23689  ldtoken  string[]
0x2368e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23693  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x23698  ldarg.0
0x23699  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x2369e  ldc.i4.0
0x2369f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x236a4  ldarg.0
0x236a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x236aa  ldc.i4.1
0x236ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x236b0  ldarg.0
0x236b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x236b6  ldnull
0x236b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x236bc  ldarg.0
0x236bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x236c2  ldstr    aRecipientemail_0// "RecipientEmails"
0x236c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x236cc  ldarg.0
0x236cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x236d2  ldnull
0x236d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x236d8  ldarg.0
0x236d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x236de  ldc.i4.0
0x236df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x236e4  ldarg.0
0x236e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x236ea  ldc.i4.0
0x236eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x236f0  ldarg.0
0x236f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x236f6  ldc.i4.0
0x236f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x236fc  ldarg.0
0x236fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>g__initLocal1
0x23702  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2::<>2__current
0x23707  ldarg.0
0x23708  ldc.i4.4
0x23709  stfld    int32 <GetProperties>d__2::<>1__state
0x2370e  ldc.i4.1
0x2370f  stloc.0
0x23710  leave.s  loc_23724
0x23712  ldarg.0
0x23713  ldc.i4.m1
0x23714  stfld    int32 <GetProperties>d__2::<>1__state
0x23719  ldc.i4.0
0x2371a  stloc.0
0x2371b  leave.s  loc_23724
0x2371d  ldarg.0
0x2371e  call     instance void <GetProperties>d__2::System.IDisposable.Dispose()
0x23723  endfinally
0x23724  ldloc.0
0x23725  ret
```
