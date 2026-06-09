# <GetProperties>d__c::MoveNext_4

- ea: `0x11ae10`
- end: `0x11b935`
- name: `<GetProperties>d__c::MoveNext_4`
- size: `2853`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x46340`
- `0x11ae10`
- `0x11b960`
- `0x11b9c0`

## string_xrefs

- `0x11aef4`: `ClientSideComponentId`
- `0x11af6e`: `ClientSideComponentId`
- `0x11afda`: `ClientSideComponentProperties`
- `0x11b047`: `ClientSideComponentProperties`
- `0x11b0b3`: `CommandUIExtension`
- `0x11b120`: `CommandUIExtension`

## pseudocode

```c

```

## disassembly

```asm
0x11ae10  ldarg.0
0x11ae11  ldfld    int32 <GetProperties>d__c::<>1__state
0x11ae16  stloc.1
0x11ae17  ldloc.1
0x11ae18  switch   loc_11AE5E, loc_11B928, loc_11AEC8, loc_11AFC1, loc_11B09A, loc_11B173, loc_11B24C, loc_11B325, loc_11B3FE, loc_11B4D8, loc_11B5B7, loc_11B696, loc_11B770, loc_11B84A, loc_11B921
0x11ae59  br       loc_11B928
0x11ae5e  ldarg.0
0x11ae5f  ldc.i4.m1
0x11ae60  stfld    int32 <GetProperties>d__c::<>1__state
0x11ae65  ldarg.0
0x11ae66  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__c::proxyContext
0x11ae6b  brtrue.s loc_11AE78
0x11ae6d  ldstr    aProxycontext// "proxyContext"
0x11ae72  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11ae77  throw
0x11ae78  ldarg.0
0x11ae79  ldarg.0
0x11ae7a  ldfld    class Microsoft.SharePoint.ServerStub.SPCustomActionElementValueTypeConverter <GetProperties>d__c::<>4__this
0x11ae7f  ldarg.0
0x11ae80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__c::proxyContext
0x11ae85  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPCustomActionElementValueTypeConverter::<>n__FabricatedMethod10(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x11ae8a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x11ae8f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__c::<>7__wrape
0x11ae94  ldarg.0
0x11ae95  ldc.i4.1
0x11ae96  stfld    int32 <GetProperties>d__c::<>1__state
0x11ae9b  br.s     loc_11AECF
0x11ae9d  ldarg.0
0x11ae9e  ldarg.0
0x11ae9f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__c::<>7__wrape
0x11aea4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x11aea9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<item>5__d
0x11aeae  ldarg.0
0x11aeaf  ldarg.0
0x11aeb0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<item>5__d
0x11aeb5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x11aeba  ldarg.0
0x11aebb  ldc.i4.2
0x11aebc  stfld    int32 <GetProperties>d__c::<>1__state
0x11aec1  ldc.i4.1
0x11aec2  stloc.0
0x11aec3  leave    loc_11B933
0x11aec8  ldarg.0
0x11aec9  ldc.i4.1
0x11aeca  stfld    int32 <GetProperties>d__c::<>1__state
0x11aecf  ldarg.0
0x11aed0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__c::<>7__wrape
0x11aed5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11aeda  brtrue.s loc_11AE9D
0x11aedc  ldarg.0
0x11aedd  call     instance void <GetProperties>d__c::<>m__Finallyf()
0x11aee2  ldarg.0
0x11aee3  ldarg.0
0x11aee4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11aee9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11aeee  ldarg.0
0x11aeef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11aef4  ldstr    aClientsidecomp// "ClientSideComponentId"
0x11aef9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11aefe  ldarg.0
0x11aeff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af04  ldc.i4.0
0x11af05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11af0a  ldarg.0
0x11af0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af10  ldc.i4.1
0x11af11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11af16  ldarg.0
0x11af17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af1c  ldc.i4.0
0x11af1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11af22  ldarg.0
0x11af23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af28  ldtoken  [mscorlib]System.Guid
0x11af2d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11af32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11af37  ldarg.0
0x11af38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af3d  ldc.i4.1
0x11af3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11af43  ldarg.0
0x11af44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af49  ldc.i4.1
0x11af4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11af4f  ldarg.0
0x11af50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af55  ldloca.s 2
0x11af57  initobj  [mscorlib]System.Guid
0x11af5d  ldloc.2
0x11af5e  box      [mscorlib]System.Guid
0x11af63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11af68  ldarg.0
0x11af69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af6e  ldstr    aClientsidecomp// "ClientSideComponentId"
0x11af73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x11af78  ldarg.0
0x11af79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af7e  ldnull
0x11af7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x11af84  ldarg.0
0x11af85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af8a  ldc.i4.0
0x11af8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x11af90  ldarg.0
0x11af91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11af96  ldc.i4.1
0x11af97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x11af9c  ldarg.0
0x11af9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11afa2  ldc.i4.0
0x11afa3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x11afa8  ldarg.0
0x11afa9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal0
0x11afae  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x11afb3  ldarg.0
0x11afb4  ldc.i4.3
0x11afb5  stfld    int32 <GetProperties>d__c::<>1__state
0x11afba  ldc.i4.1
0x11afbb  stloc.0
0x11afbc  leave    loc_11B933
0x11afc1  ldarg.0
0x11afc2  ldc.i4.m1
0x11afc3  stfld    int32 <GetProperties>d__c::<>1__state
0x11afc8  ldarg.0
0x11afc9  ldarg.0
0x11afca  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11afcf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11afd4  ldarg.0
0x11afd5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11afda  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x11afdf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11afe4  ldarg.0
0x11afe5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11afea  ldc.i4.0
0x11afeb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11aff0  ldarg.0
0x11aff1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11aff6  ldc.i4.1
0x11aff7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11affc  ldarg.0
0x11affd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b002  ldc.i4.0
0x11b003  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11b008  ldarg.0
0x11b009  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b00e  ldtoken  [mscorlib]System.String
0x11b013  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11b018  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11b01d  ldarg.0
0x11b01e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b023  ldc.i4.1
0x11b024  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11b029  ldarg.0
0x11b02a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b02f  ldc.i4.1
0x11b030  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11b035  ldarg.0
0x11b036  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b03b  ldnull
0x11b03c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11b041  ldarg.0
0x11b042  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b047  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x11b04c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x11b051  ldarg.0
0x11b052  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b057  ldnull
0x11b058  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x11b05d  ldarg.0
0x11b05e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b063  ldc.i4.0
0x11b064  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x11b069  ldarg.0
0x11b06a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b06f  ldc.i4.1
0x11b070  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x11b075  ldarg.0
0x11b076  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b07b  ldc.i4.0
0x11b07c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x11b081  ldarg.0
0x11b082  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal1
0x11b087  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x11b08c  ldarg.0
0x11b08d  ldc.i4.4
0x11b08e  stfld    int32 <GetProperties>d__c::<>1__state
0x11b093  ldc.i4.1
0x11b094  stloc.0
0x11b095  leave    loc_11B933
0x11b09a  ldarg.0
0x11b09b  ldc.i4.m1
0x11b09c  stfld    int32 <GetProperties>d__c::<>1__state
0x11b0a1  ldarg.0
0x11b0a2  ldarg.0
0x11b0a3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11b0a8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b0ad  ldarg.0
0x11b0ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b0b3  ldstr    aCommanduiexten// "CommandUIExtension"
0x11b0b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11b0bd  ldarg.0
0x11b0be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b0c3  ldc.i4.0
0x11b0c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11b0c9  ldarg.0
0x11b0ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b0cf  ldc.i4.1
0x11b0d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11b0d5  ldarg.0
0x11b0d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b0db  ldc.i4.0
0x11b0dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11b0e1  ldarg.0
0x11b0e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b0e7  ldtoken  [mscorlib]System.String
0x11b0ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11b0f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11b0f6  ldarg.0
0x11b0f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b0fc  ldc.i4.1
0x11b0fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11b102  ldarg.0
0x11b103  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b108  ldc.i4.1
0x11b109  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11b10e  ldarg.0
0x11b10f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b114  ldnull
0x11b115  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11b11a  ldarg.0
0x11b11b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b120  ldstr    aCommanduiexten// "CommandUIExtension"
0x11b125  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x11b12a  ldarg.0
0x11b12b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b130  ldnull
0x11b131  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x11b136  ldarg.0
0x11b137  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b13c  ldc.i4.0
0x11b13d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x11b142  ldarg.0
0x11b143  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b148  ldc.i4.0
0x11b149  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x11b14e  ldarg.0
0x11b14f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b154  ldc.i4.0
0x11b155  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x11b15a  ldarg.0
0x11b15b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal2
0x11b160  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x11b165  ldarg.0
0x11b166  ldc.i4.5
0x11b167  stfld    int32 <GetProperties>d__c::<>1__state
0x11b16c  ldc.i4.1
0x11b16d  stloc.0
0x11b16e  leave    loc_11B933
0x11b173  ldarg.0
0x11b174  ldc.i4.m1
0x11b175  stfld    int32 <GetProperties>d__c::<>1__state
0x11b17a  ldarg.0
0x11b17b  ldarg.0
0x11b17c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11b181  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b186  ldarg.0
0x11b187  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b18c  ldstr    aEnabledscript// "EnabledScript"
0x11b191  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11b196  ldarg.0
0x11b197  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b19c  ldc.i4.0
0x11b19d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11b1a2  ldarg.0
0x11b1a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b1a8  ldc.i4.1
0x11b1a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11b1ae  ldarg.0
0x11b1af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b1b4  ldc.i4.0
0x11b1b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11b1ba  ldarg.0
0x11b1bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b1c0  ldtoken  [mscorlib]System.String
0x11b1c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11b1ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11b1cf  ldarg.0
0x11b1d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b1d5  ldc.i4.1
0x11b1d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11b1db  ldarg.0
0x11b1dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b1e1  ldc.i4.1
0x11b1e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11b1e7  ldarg.0
0x11b1e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
0x11b1ed  ldnull
0x11b1ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11b1f3  ldarg.0
0x11b1f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal3
  ... truncated ...
```
