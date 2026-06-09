# <GetProperties>d__13::MoveNext_1

- ea: `0x1369b0`
- end: `0x137246`
- name: `<GetProperties>d__13::MoveNext_1`
- size: `2198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x5ce50`
- `0x1369b0`
- `0x137270`
- `0x1372d0`

## string_xrefs

- `0x136b61`: `Created`
- `0x136bdb`: `Created`
- `0x136c47`: `CreatedBy`
- `0x136a88`: `CheckInComment`
- `0x136af5`: `CheckInComment`
- `0x136cb4`: `CreatedBy_Client`

## pseudocode

```c

```

## disassembly

```asm
0x1369b0  ldarg.0
0x1369b1  ldfld    int32 <GetProperties>d__13::<>1__state
0x1369b6  stloc.1
0x1369b7  ldloc.1
0x1369b8  switch   loc_1369F2, loc_137239, loc_136A5C, loc_136B48, loc_136C2E, loc_136D07, loc_136DE5, loc_136EC3, loc_136FA2, loc_137081, loc_13715B, loc_137232
0x1369ed  br       loc_137239
0x1369f2  ldarg.0
0x1369f3  ldc.i4.m1
0x1369f4  stfld    int32 <GetProperties>d__13::<>1__state
0x1369f9  ldarg.0
0x1369fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__13::proxyContext
0x1369ff  brtrue.s loc_136A0C
0x136a01  ldstr    aProxycontext// "proxyContext"
0x136a06  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x136a0b  throw
0x136a0c  ldarg.0
0x136a0d  ldarg.0
0x136a0e  ldfld    class Microsoft.SharePoint.ServerStub.SPFileVersionServerStub <GetProperties>d__13::<>4__this
0x136a13  ldarg.0
0x136a14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__13::proxyContext
0x136a19  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPFileVersionServerStub::<>n__FabricatedMethod17(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x136a1e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x136a23  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__13::<>7__wrap15
0x136a28  ldarg.0
0x136a29  ldc.i4.1
0x136a2a  stfld    int32 <GetProperties>d__13::<>1__state
0x136a2f  br.s     loc_136A63
0x136a31  ldarg.0
0x136a32  ldarg.0
0x136a33  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__13::<>7__wrap15
0x136a38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x136a3d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<item>5__14
0x136a42  ldarg.0
0x136a43  ldarg.0
0x136a44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<item>5__14
0x136a49  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x136a4e  ldarg.0
0x136a4f  ldc.i4.2
0x136a50  stfld    int32 <GetProperties>d__13::<>1__state
0x136a55  ldc.i4.1
0x136a56  stloc.0
0x136a57  leave    loc_137244
0x136a5c  ldarg.0
0x136a5d  ldc.i4.1
0x136a5e  stfld    int32 <GetProperties>d__13::<>1__state
0x136a63  ldarg.0
0x136a64  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__13::<>7__wrap15
0x136a69  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x136a6e  brtrue.s loc_136A31
0x136a70  ldarg.0
0x136a71  call     instance void <GetProperties>d__13::<>m__Finally16()
0x136a76  ldarg.0
0x136a77  ldarg.0
0x136a78  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x136a7d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136a82  ldarg.0
0x136a83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136a88  ldstr    aCheckincomment_0// "CheckInComment"
0x136a8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x136a92  ldarg.0
0x136a93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136a98  ldc.i4.0
0x136a99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x136a9e  ldarg.0
0x136a9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136aa4  ldc.i4.1
0x136aa5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x136aaa  ldarg.0
0x136aab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136ab0  ldc.i4.0
0x136ab1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x136ab6  ldarg.0
0x136ab7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136abc  ldtoken  [mscorlib]System.String
0x136ac1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x136ac6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x136acb  ldarg.0
0x136acc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136ad1  ldc.i4.1
0x136ad2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x136ad7  ldarg.0
0x136ad8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136add  ldc.i4.1
0x136ade  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x136ae3  ldarg.0
0x136ae4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136ae9  ldnull
0x136aea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x136aef  ldarg.0
0x136af0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136af5  ldstr    aCheckincomment_0// "CheckInComment"
0x136afa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x136aff  ldarg.0
0x136b00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136b05  ldnull
0x136b06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x136b0b  ldarg.0
0x136b0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136b11  ldc.i4.0
0x136b12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x136b17  ldarg.0
0x136b18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136b1d  ldc.i4.0
0x136b1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x136b23  ldarg.0
0x136b24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136b29  ldc.i4.0
0x136b2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x136b2f  ldarg.0
0x136b30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x136b35  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x136b3a  ldarg.0
0x136b3b  ldc.i4.3
0x136b3c  stfld    int32 <GetProperties>d__13::<>1__state
0x136b41  ldc.i4.1
0x136b42  stloc.0
0x136b43  leave    loc_137244
0x136b48  ldarg.0
0x136b49  ldc.i4.m1
0x136b4a  stfld    int32 <GetProperties>d__13::<>1__state
0x136b4f  ldarg.0
0x136b50  ldarg.0
0x136b51  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x136b56  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136b5b  ldarg.0
0x136b5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136b61  ldstr    aCreated// "Created"
0x136b66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x136b6b  ldarg.0
0x136b6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136b71  ldc.i4.0
0x136b72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x136b77  ldarg.0
0x136b78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136b7d  ldc.i4.1
0x136b7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x136b83  ldarg.0
0x136b84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136b89  ldc.i4.0
0x136b8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x136b8f  ldarg.0
0x136b90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136b95  ldtoken  [mscorlib]System.DateTime
0x136b9a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x136b9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x136ba4  ldarg.0
0x136ba5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136baa  ldc.i4.1
0x136bab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x136bb0  ldarg.0
0x136bb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136bb6  ldc.i4.1
0x136bb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x136bbc  ldarg.0
0x136bbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136bc2  ldloca.s 2
0x136bc4  initobj  [mscorlib]System.DateTime
0x136bca  ldloc.2
0x136bcb  box      [mscorlib]System.DateTime
0x136bd0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x136bd5  ldarg.0
0x136bd6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136bdb  ldstr    aCreated// "Created"
0x136be0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x136be5  ldarg.0
0x136be6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136beb  ldnull
0x136bec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x136bf1  ldarg.0
0x136bf2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136bf7  ldc.i4.0
0x136bf8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x136bfd  ldarg.0
0x136bfe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136c03  ldc.i4.0
0x136c04  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x136c09  ldarg.0
0x136c0a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136c0f  ldc.i4.0
0x136c10  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x136c15  ldarg.0
0x136c16  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x136c1b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x136c20  ldarg.0
0x136c21  ldc.i4.4
0x136c22  stfld    int32 <GetProperties>d__13::<>1__state
0x136c27  ldc.i4.1
0x136c28  stloc.0
0x136c29  leave    loc_137244
0x136c2e  ldarg.0
0x136c2f  ldc.i4.m1
0x136c30  stfld    int32 <GetProperties>d__13::<>1__state
0x136c35  ldarg.0
0x136c36  ldarg.0
0x136c37  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x136c3c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c41  ldarg.0
0x136c42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c47  ldstr    aCreatedby// "CreatedBy"
0x136c4c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x136c51  ldarg.0
0x136c52  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c57  ldc.i4.0
0x136c58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x136c5d  ldarg.0
0x136c5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c63  ldc.i4.4
0x136c64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x136c69  ldarg.0
0x136c6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c6f  ldc.i4.0
0x136c70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x136c75  ldarg.0
0x136c76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c7b  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x136c80  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x136c85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x136c8a  ldarg.0
0x136c8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c90  ldc.i4.1
0x136c91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x136c96  ldarg.0
0x136c97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136c9c  ldc.i4.1
0x136c9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x136ca2  ldarg.0
0x136ca3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136ca8  ldnull
0x136ca9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x136cae  ldarg.0
0x136caf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136cb4  ldstr    aCreatedbyClien// "CreatedBy_Client"
0x136cb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x136cbe  ldarg.0
0x136cbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136cc4  ldnull
0x136cc5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x136cca  ldarg.0
0x136ccb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136cd0  ldc.i4.0
0x136cd1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x136cd6  ldarg.0
0x136cd7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136cdc  ldc.i4.0
0x136cdd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x136ce2  ldarg.0
0x136ce3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136ce8  ldc.i4.0
0x136ce9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x136cee  ldarg.0
0x136cef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x136cf4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x136cf9  ldarg.0
0x136cfa  ldc.i4.5
0x136cfb  stfld    int32 <GetProperties>d__13::<>1__state
0x136d00  ldc.i4.1
0x136d01  stloc.0
0x136d02  leave    loc_137244
0x136d07  ldarg.0
0x136d08  ldc.i4.m1
0x136d09  stfld    int32 <GetProperties>d__13::<>1__state
0x136d0e  ldarg.0
0x136d0f  ldarg.0
0x136d10  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x136d15  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d1a  ldarg.0
0x136d1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d20  ldstr    aId_1// "ID"
0x136d25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x136d2a  ldarg.0
0x136d2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d30  ldc.i4.0
0x136d31  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x136d36  ldarg.0
0x136d37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d3c  ldc.i4.1
0x136d3d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x136d42  ldarg.0
0x136d43  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d48  ldc.i4.0
0x136d49  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x136d4e  ldarg.0
0x136d4f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d54  ldtoken  [mscorlib]System.Int32
0x136d59  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x136d5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x136d63  ldarg.0
0x136d64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d69  ldc.i4.1
0x136d6a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x136d6f  ldarg.0
0x136d70  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d75  ldc.i4.1
0x136d76  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x136d7b  ldarg.0
0x136d7c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x136d81  ldc.i4.0
0x136d82  box      [mscorlib]System.Int32
0x136d87  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x136d8c  ldarg.0
  ... truncated ...
```
