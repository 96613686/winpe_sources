# <GetProperties>d__23::MoveNext

- ea: `0x10ed60`
- end: `0x110d0a`
- name: `<GetProperties>d__23::MoveNext`
- size: `8106`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x3ea40`
- `0x10ed60`
- `0x110d30`
- `0x110d90`

## string_xrefs

- `0x110996`: `Update`
- `0x110a08`: `Update`
- `0x10f3ca`: `DeleteObject`
- `0x10f43c`: `Delete`
- `0x1108b7`: `SystemUpdate`
- `0x110929`: `SystemUpdate`
- `0x110001`: `Rename`
- `0x110073`: `Rename`
- `0x10f13a`: `ChangeTokenEnd`
- `0x10f1a7`: `ChangeTokenEnd`
- `0x10f213`: `ChangeTokenStart`
- `0x10f280`: `ChangeTokenStart`
- `0x10f9e8`: `GroupMembershipDelete`
- `0x10fa5a`: `GroupMembershipDelete`
- `0x1100e0`: `RequireSecurityTrim`
- `0x110152`: `RequireSecurityTrim`
- `0x11037d`: `RoleAssignmentDelete`
- `0x1103ef`: `RoleAssignmentDelete`
- `0x11053b`: `RoleDefinitionDelete`
- `0x1105ad`: `RoleDefinitionDelete`
- `0x11061a`: `RoleDefinitionUpdate`
- `0x11068c`: `RoleDefinitionUpdate`
- `0x1106f9`: `SecurityPolicy`
- `0x11076b`: `SecurityPolicy`

## pseudocode

```c

```

## disassembly

```asm
0x10ed60  ldarg.0
0x10ed61  ldfld    int32 <GetProperties>d__23::<>1__state
0x10ed66  stloc.1
0x10ed67  ldloc.1
0x10ed68  switch   loc_10EE0A, loc_110CFD, loc_10EE74, loc_10EF65, loc_10F043, loc_10F121, loc_10F1FA, loc_10F2D3, loc_10F3B1, loc_10F490, loc_10F574, loc_10F653, loc_10F732, loc_10F811, loc_10F8F0, loc_10F9CF, loc_10FAAE, loc_10FB8D, loc_10FC6C, loc_10FD4B, loc_10FE2A, loc_10FF09, loc_10FFE8, loc_1100C7, loc_1101A6, loc_110285, loc_110364, loc_110443, loc_110522, loc_110601, loc_1106E0, loc_1107BF, loc_11089E, loc_11097D, loc_110A5C, loc_110B3B, loc_110C1A, loc_110CF6
0x10ee05  br       loc_110CFD
0x10ee0a  ldarg.0
0x10ee0b  ldc.i4.m1
0x10ee0c  stfld    int32 <GetProperties>d__23::<>1__state
0x10ee11  ldarg.0
0x10ee12  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__23::proxyContext
0x10ee17  brtrue.s loc_10EE24
0x10ee19  ldstr    aProxycontext// "proxyContext"
0x10ee1e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10ee23  throw
0x10ee24  ldarg.0
0x10ee25  ldarg.0
0x10ee26  ldfld    class Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter <GetProperties>d__23::<>4__this
0x10ee2b  ldarg.0
0x10ee2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__23::proxyContext
0x10ee31  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::<>n__FabricatedMethod27(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext name)
0x10ee36  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x10ee3b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__23::<>7__wrap25
0x10ee40  ldarg.0
0x10ee41  ldc.i4.1
0x10ee42  stfld    int32 <GetProperties>d__23::<>1__state
0x10ee47  br.s     loc_10EE7B
0x10ee49  ldarg.0
0x10ee4a  ldarg.0
0x10ee4b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__23::<>7__wrap25
0x10ee50  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x10ee55  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<item>5__24
0x10ee5a  ldarg.0
0x10ee5b  ldarg.0
0x10ee5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<item>5__24
0x10ee61  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>2__current
0x10ee66  ldarg.0
0x10ee67  ldc.i4.2
0x10ee68  stfld    int32 <GetProperties>d__23::<>1__state
0x10ee6d  ldc.i4.1
0x10ee6e  stloc.0
0x10ee6f  leave    loc_110D08
0x10ee74  ldarg.0
0x10ee75  ldc.i4.1
0x10ee76  stfld    int32 <GetProperties>d__23::<>1__state
0x10ee7b  ldarg.0
0x10ee7c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__23::<>7__wrap25
0x10ee81  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10ee86  brtrue.s loc_10EE49
0x10ee88  ldarg.0
0x10ee89  call     instance void <GetProperties>d__23::<>m__Finally26()
0x10ee8e  ldarg.0
0x10ee8f  ldarg.0
0x10ee90  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x10ee95  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ee9a  ldarg.0
0x10ee9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10eea0  ldstr    aActivity// "Activity"
0x10eea5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x10eeaa  ldarg.0
0x10eeab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10eeb0  ldc.i4.0
0x10eeb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x10eeb6  ldarg.0
0x10eeb7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10eebc  ldc.i4.1
0x10eebd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x10eec2  ldarg.0
0x10eec3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10eec8  ldc.i4.0
0x10eec9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x10eece  ldarg.0
0x10eecf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10eed4  ldtoken  [mscorlib]System.Boolean
0x10eed9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10eede  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x10eee3  ldarg.0
0x10eee4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10eee9  ldc.i4.0
0x10eeea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x10eeef  ldarg.0
0x10eef0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10eef5  ldc.i4.1
0x10eef6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x10eefb  ldarg.0
0x10eefc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ef01  ldc.i4.0
0x10ef02  box      [mscorlib]System.Boolean
0x10ef07  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x10ef0c  ldarg.0
0x10ef0d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ef12  ldstr    aActivity// "Activity"
0x10ef17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x10ef1c  ldarg.0
0x10ef1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ef22  ldnull
0x10ef23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x10ef28  ldarg.0
0x10ef29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ef2e  ldc.i4.0
0x10ef2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x10ef34  ldarg.0
0x10ef35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ef3a  ldc.i4.0
0x10ef3b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x10ef40  ldarg.0
0x10ef41  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ef46  ldc.i4.0
0x10ef47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x10ef4c  ldarg.0
0x10ef4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal0
0x10ef52  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>2__current
0x10ef57  ldarg.0
0x10ef58  ldc.i4.3
0x10ef59  stfld    int32 <GetProperties>d__23::<>1__state
0x10ef5e  ldc.i4.1
0x10ef5f  stloc.0
0x10ef60  leave    loc_110D08
0x10ef65  ldarg.0
0x10ef66  ldc.i4.m1
0x10ef67  stfld    int32 <GetProperties>d__23::<>1__state
0x10ef6c  ldarg.0
0x10ef6d  ldarg.0
0x10ef6e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x10ef73  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10ef78  ldarg.0
0x10ef79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10ef7e  ldstr    aAdd// "Add"
0x10ef83  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x10ef88  ldarg.0
0x10ef89  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10ef8e  ldc.i4.0
0x10ef8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x10ef94  ldarg.0
0x10ef95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10ef9a  ldc.i4.1
0x10ef9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x10efa0  ldarg.0
0x10efa1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10efa6  ldc.i4.0
0x10efa7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x10efac  ldarg.0
0x10efad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10efb2  ldtoken  [mscorlib]System.Boolean
0x10efb7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10efbc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x10efc1  ldarg.0
0x10efc2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10efc7  ldc.i4.0
0x10efc8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x10efcd  ldarg.0
0x10efce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10efd3  ldc.i4.1
0x10efd4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x10efd9  ldarg.0
0x10efda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10efdf  ldc.i4.0
0x10efe0  box      [mscorlib]System.Boolean
0x10efe5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x10efea  ldarg.0
0x10efeb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10eff0  ldstr    aAdd// "Add"
0x10eff5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x10effa  ldarg.0
0x10effb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10f000  ldnull
0x10f001  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x10f006  ldarg.0
0x10f007  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10f00c  ldc.i4.0
0x10f00d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x10f012  ldarg.0
0x10f013  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10f018  ldc.i4.0
0x10f019  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x10f01e  ldarg.0
0x10f01f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10f024  ldc.i4.0
0x10f025  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x10f02a  ldarg.0
0x10f02b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal1
0x10f030  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>2__current
0x10f035  ldarg.0
0x10f036  ldc.i4.4
0x10f037  stfld    int32 <GetProperties>d__23::<>1__state
0x10f03c  ldc.i4.1
0x10f03d  stloc.0
0x10f03e  leave    loc_110D08
0x10f043  ldarg.0
0x10f044  ldc.i4.m1
0x10f045  stfld    int32 <GetProperties>d__23::<>1__state
0x10f04a  ldarg.0
0x10f04b  ldarg.0
0x10f04c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x10f051  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f056  ldarg.0
0x10f057  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f05c  ldstr    aAlert// "Alert"
0x10f061  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x10f066  ldarg.0
0x10f067  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f06c  ldc.i4.0
0x10f06d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x10f072  ldarg.0
0x10f073  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f078  ldc.i4.1
0x10f079  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x10f07e  ldarg.0
0x10f07f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f084  ldc.i4.0
0x10f085  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x10f08a  ldarg.0
0x10f08b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f090  ldtoken  [mscorlib]System.Boolean
0x10f095  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10f09a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x10f09f  ldarg.0
0x10f0a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f0a5  ldc.i4.0
0x10f0a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x10f0ab  ldarg.0
0x10f0ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f0b1  ldc.i4.1
0x10f0b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x10f0b7  ldarg.0
0x10f0b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f0bd  ldc.i4.0
0x10f0be  box      [mscorlib]System.Boolean
0x10f0c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x10f0c8  ldarg.0
0x10f0c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f0ce  ldstr    aAlert// "Alert"
0x10f0d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x10f0d8  ldarg.0
0x10f0d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f0de  ldnull
0x10f0df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x10f0e4  ldarg.0
0x10f0e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f0ea  ldc.i4.0
0x10f0eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x10f0f0  ldarg.0
0x10f0f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f0f6  ldc.i4.0
0x10f0f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x10f0fc  ldarg.0
0x10f0fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f102  ldc.i4.0
0x10f103  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x10f108  ldarg.0
0x10f109  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal2
0x10f10e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>2__current
0x10f113  ldarg.0
0x10f114  ldc.i4.5
0x10f115  stfld    int32 <GetProperties>d__23::<>1__state
0x10f11a  ldc.i4.1
0x10f11b  stloc.0
0x10f11c  leave    loc_110D08
0x10f121  ldarg.0
0x10f122  ldc.i4.m1
0x10f123  stfld    int32 <GetProperties>d__23::<>1__state
0x10f128  ldarg.0
0x10f129  ldarg.0
0x10f12a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x10f12f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f134  ldarg.0
0x10f135  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f13a  ldstr    aChangetokenend// "ChangeTokenEnd"
0x10f13f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x10f144  ldarg.0
0x10f145  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f14a  ldc.i4.0
0x10f14b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x10f150  ldarg.0
0x10f151  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f156  ldc.i4.2
0x10f157  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x10f15c  ldarg.0
0x10f15d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f162  ldc.i4.0
0x10f163  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x10f168  ldarg.0
0x10f169  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f16e  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken
0x10f173  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10f178  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x10f17d  ldarg.0
0x10f17e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f183  ldc.i4.0
0x10f184  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x10f189  ldarg.0
0x10f18a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f18f  ldc.i4.1
0x10f190  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x10f195  ldarg.0
0x10f196  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
0x10f19b  ldnull
0x10f19c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x10f1a1  ldarg.0
0x10f1a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__23::<>g__initLocal3
  ... truncated ...
```
