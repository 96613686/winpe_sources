# <GetProperties>d__4::MoveNext_2

- ea: `0x2b520`
- end: `0x2b940`
- name: `<GetProperties>d__4::MoveNext_2`
- size: `1056`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x12c10`
- `0x2b520`
- `0x2b960`
- `0x2b9c0`

## pseudocode

```c

```

## disassembly

```asm
0x2b520  ldarg.0
0x2b521  ldfld    int32 <GetProperties>d__4::<>1__state
0x2b526  stloc.1
0x2b527  ldloc.1
0x2b528  switch   loc_2B54E, loc_2B933, loc_2B5B8, loc_2B6A4, loc_2B77D, loc_2B856, loc_2B92C
0x2b549  br       loc_2B933
0x2b54e  ldarg.0
0x2b54f  ldc.i4.m1
0x2b550  stfld    int32 <GetProperties>d__4::<>1__state
0x2b555  ldarg.0
0x2b556  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x2b55b  brtrue.s loc_2B568
0x2b55d  ldstr    aProxycontext// "proxyContext"
0x2b562  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2b567  throw
0x2b568  ldarg.0
0x2b569  ldarg.0
0x2b56a  ldfld    class Microsoft.SharePoint.Publishing.UserInfoServerStub <GetProperties>d__4::<>4__this
0x2b56f  ldarg.0
0x2b570  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x2b575  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.UserInfoServerStub::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x2b57a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x2b57f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x2b584  ldarg.0
0x2b585  ldc.i4.1
0x2b586  stfld    int32 <GetProperties>d__4::<>1__state
0x2b58b  br.s     loc_2B5BF
0x2b58d  ldarg.0
0x2b58e  ldarg.0
0x2b58f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x2b594  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x2b599  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x2b59e  ldarg.0
0x2b59f  ldarg.0
0x2b5a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x2b5a5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2b5aa  ldarg.0
0x2b5ab  ldc.i4.2
0x2b5ac  stfld    int32 <GetProperties>d__4::<>1__state
0x2b5b1  ldc.i4.1
0x2b5b2  stloc.0
0x2b5b3  leave    loc_2B93E
0x2b5b8  ldarg.0
0x2b5b9  ldc.i4.1
0x2b5ba  stfld    int32 <GetProperties>d__4::<>1__state
0x2b5bf  ldarg.0
0x2b5c0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x2b5c5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b5ca  brtrue.s loc_2B58D
0x2b5cc  ldarg.0
0x2b5cd  call     instance void <GetProperties>d__4::<>m__Finally7()
0x2b5d2  ldarg.0
0x2b5d3  ldarg.0
0x2b5d4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2b5d9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b5de  ldarg.0
0x2b5df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b5e4  ldstr    aAccountname// "AccountName"
0x2b5e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2b5ee  ldarg.0
0x2b5ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b5f4  ldc.i4.0
0x2b5f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2b5fa  ldarg.0
0x2b5fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b600  ldc.i4.1
0x2b601  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2b606  ldarg.0
0x2b607  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b60c  ldc.i4.0
0x2b60d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2b612  ldarg.0
0x2b613  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b618  ldtoken  [mscorlib]System.String
0x2b61d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b622  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2b627  ldarg.0
0x2b628  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b62d  ldc.i4.0
0x2b62e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2b633  ldarg.0
0x2b634  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b639  ldc.i4.1
0x2b63a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2b63f  ldarg.0
0x2b640  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b645  ldnull
0x2b646  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2b64b  ldarg.0
0x2b64c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b651  ldstr    aAccountname// "AccountName"
0x2b656  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2b65b  ldarg.0
0x2b65c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b661  ldnull
0x2b662  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2b667  ldarg.0
0x2b668  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b66d  ldc.i4.0
0x2b66e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2b673  ldarg.0
0x2b674  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b679  ldc.i4.1
0x2b67a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2b67f  ldarg.0
0x2b680  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b685  ldc.i4.0
0x2b686  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2b68b  ldarg.0
0x2b68c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2b691  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2b696  ldarg.0
0x2b697  ldc.i4.3
0x2b698  stfld    int32 <GetProperties>d__4::<>1__state
0x2b69d  ldc.i4.1
0x2b69e  stloc.0
0x2b69f  leave    loc_2B93E
0x2b6a4  ldarg.0
0x2b6a5  ldc.i4.m1
0x2b6a6  stfld    int32 <GetProperties>d__4::<>1__state
0x2b6ab  ldarg.0
0x2b6ac  ldarg.0
0x2b6ad  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2b6b2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b6b7  ldarg.0
0x2b6b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b6bd  ldstr    aAcronym// "Acronym"
0x2b6c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2b6c7  ldarg.0
0x2b6c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b6cd  ldc.i4.0
0x2b6ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2b6d3  ldarg.0
0x2b6d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b6d9  ldc.i4.1
0x2b6da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2b6df  ldarg.0
0x2b6e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b6e5  ldc.i4.0
0x2b6e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2b6eb  ldarg.0
0x2b6ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b6f1  ldtoken  [mscorlib]System.String
0x2b6f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b6fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2b700  ldarg.0
0x2b701  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b706  ldc.i4.0
0x2b707  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2b70c  ldarg.0
0x2b70d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b712  ldc.i4.1
0x2b713  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2b718  ldarg.0
0x2b719  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b71e  ldnull
0x2b71f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2b724  ldarg.0
0x2b725  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b72a  ldstr    aAcronym// "Acronym"
0x2b72f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2b734  ldarg.0
0x2b735  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b73a  ldnull
0x2b73b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2b740  ldarg.0
0x2b741  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b746  ldc.i4.0
0x2b747  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2b74c  ldarg.0
0x2b74d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b752  ldc.i4.1
0x2b753  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2b758  ldarg.0
0x2b759  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b75e  ldc.i4.0
0x2b75f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2b764  ldarg.0
0x2b765  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2b76a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2b76f  ldarg.0
0x2b770  ldc.i4.4
0x2b771  stfld    int32 <GetProperties>d__4::<>1__state
0x2b776  ldc.i4.1
0x2b777  stloc.0
0x2b778  leave    loc_2B93E
0x2b77d  ldarg.0
0x2b77e  ldc.i4.m1
0x2b77f  stfld    int32 <GetProperties>d__4::<>1__state
0x2b784  ldarg.0
0x2b785  ldarg.0
0x2b786  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2b78b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b790  ldarg.0
0x2b791  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b796  ldstr    aColor// "Color"
0x2b79b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2b7a0  ldarg.0
0x2b7a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b7a6  ldc.i4.0
0x2b7a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2b7ac  ldarg.0
0x2b7ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b7b2  ldc.i4.1
0x2b7b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2b7b8  ldarg.0
0x2b7b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b7be  ldc.i4.0
0x2b7bf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2b7c4  ldarg.0
0x2b7c5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b7ca  ldtoken  [mscorlib]System.String
0x2b7cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b7d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2b7d9  ldarg.0
0x2b7da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b7df  ldc.i4.0
0x2b7e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2b7e5  ldarg.0
0x2b7e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b7eb  ldc.i4.1
0x2b7ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2b7f1  ldarg.0
0x2b7f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b7f7  ldnull
0x2b7f8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2b7fd  ldarg.0
0x2b7fe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b803  ldstr    aColor// "Color"
0x2b808  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2b80d  ldarg.0
0x2b80e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b813  ldnull
0x2b814  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2b819  ldarg.0
0x2b81a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b81f  ldc.i4.0
0x2b820  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2b825  ldarg.0
0x2b826  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b82b  ldc.i4.1
0x2b82c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2b831  ldarg.0
0x2b832  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b837  ldc.i4.0
0x2b838  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2b83d  ldarg.0
0x2b83e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2b843  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2b848  ldarg.0
0x2b849  ldc.i4.5
0x2b84a  stfld    int32 <GetProperties>d__4::<>1__state
0x2b84f  ldc.i4.1
0x2b850  stloc.0
0x2b851  leave    loc_2B93E
0x2b856  ldarg.0
0x2b857  ldc.i4.m1
0x2b858  stfld    int32 <GetProperties>d__4::<>1__state
0x2b85d  ldarg.0
0x2b85e  ldarg.0
0x2b85f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2b864  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b869  ldarg.0
0x2b86a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b86f  ldstr    aName// "Name"
0x2b874  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2b879  ldarg.0
0x2b87a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b87f  ldc.i4.0
0x2b880  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2b885  ldarg.0
0x2b886  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b88b  ldc.i4.1
0x2b88c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2b891  ldarg.0
0x2b892  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b897  ldc.i4.0
0x2b898  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2b89d  ldarg.0
0x2b89e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b8a3  ldtoken  [mscorlib]System.String
0x2b8a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b8ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2b8b2  ldarg.0
0x2b8b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b8b8  ldc.i4.0
0x2b8b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2b8be  ldarg.0
0x2b8bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b8c4  ldc.i4.1
0x2b8c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2b8ca  ldarg.0
0x2b8cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b8d0  ldnull
0x2b8d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2b8d6  ldarg.0
0x2b8d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2b8dc  ldstr    aName// "Name"
0x2b8e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2b8e6  ldarg.0
  ... truncated ...
```
