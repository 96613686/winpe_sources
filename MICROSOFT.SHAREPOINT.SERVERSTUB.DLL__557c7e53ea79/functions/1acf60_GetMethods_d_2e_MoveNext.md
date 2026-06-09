# <GetMethods>d__2e::MoveNext

- ea: `0x1acf60`
- end: `0x1ae9d6`
- name: `<GetMethods>d__2e::MoveNext`
- size: `6774`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0xb1700`
- `0x1acf60`
- `0x1aea00`
- `0x1aea60`

## string_xrefs

- `0x1ad3d6`: `ForwardObjectLink`
- `0x1ad40a`: `ForwardObjectLink`
- `0x1adea8`: `propagateAcl`
- `0x1ae94c`: `propagateAcl`
- `0x1adf9c`: `includeAnonymousLinkInEmail`
- `0x1ad345`: `linkKind`
- `0x1ae2d8`: `linkKind`
- `0x1ae534`: `UpdateDocumentSharingInfo`
- `0x1ae568`: `UpdateDocumentSharingInfo`
- `0x1ae8d2`: `includeAnonymousLinksInNotification`
- `0x1ada31`: `ShareLink`
- `0x1ada65`: `ShareLink`
- `0x1ad209`: `DeleteLinkByKind`
- `0x1ad23d`: `DeleteLinkByKind`
- `0x1ae19c`: `UnshareLink`
- `0x1ae1d0`: `UnshareLink`

## pseudocode

```c

```

## disassembly

```asm
0x1acf60  ldarg.0
0x1acf61  ldfld    int32 <GetMethods>d__2e::<>1__state
0x1acf66  stloc.1
0x1acf67  ldloc.1
0x1acf68  switch   loc_1ACFA6, loc_1AE9C9, loc_1AD010, loc_1AD1F0, loc_1AD3BD, loc_1AD67E, loc_1AD84B, loc_1ADA18, loc_1ADBE5, loc_1AE183, loc_1AE3C7, loc_1AE51B, loc_1AE9C2
0x1acfa1  br       loc_1AE9C9
0x1acfa6  ldarg.0
0x1acfa7  ldc.i4.m1
0x1acfa8  stfld    int32 <GetMethods>d__2e::<>1__state
0x1acfad  ldarg.0
0x1acfae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2e::proxyContext
0x1acfb3  brtrue.s loc_1ACFC0
0x1acfb5  ldstr    aProxycontext// "proxyContext"
0x1acfba  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1acfbf  throw
0x1acfc0  ldarg.0
0x1acfc1  ldarg.0
0x1acfc2  ldfld    class Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub <GetMethods>d__2e::<>4__this
0x1acfc7  ldarg.0
0x1acfc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2e::proxyContext
0x1acfcd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::<>n__FabricatedMethod33(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x1acfd2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1acfd7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2e::<>7__wrap31
0x1acfdc  ldarg.0
0x1acfdd  ldc.i4.1
0x1acfde  stfld    int32 <GetMethods>d__2e::<>1__state
0x1acfe3  br.s     loc_1AD017
0x1acfe5  ldarg.0
0x1acfe6  ldarg.0
0x1acfe7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2e::<>7__wrap31
0x1acfec  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1acff1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<itemBase>5__2f
0x1acff6  ldarg.0
0x1acff7  ldarg.0
0x1acff8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<itemBase>5__2f
0x1acffd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>2__current
0x1ad002  ldarg.0
0x1ad003  ldc.i4.2
0x1ad004  stfld    int32 <GetMethods>d__2e::<>1__state
0x1ad009  ldc.i4.1
0x1ad00a  stloc.0
0x1ad00b  leave    loc_1AE9D4
0x1ad010  ldarg.0
0x1ad011  ldc.i4.1
0x1ad012  stfld    int32 <GetMethods>d__2e::<>1__state
0x1ad017  ldarg.0
0x1ad018  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2e::<>7__wrap31
0x1ad01d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ad022  brtrue.s loc_1ACFE5
0x1ad024  ldarg.0
0x1ad025  call     instance void <GetMethods>d__2e::<>m__Finally32()
0x1ad02a  ldarg.0
0x1ad02b  ldarg.0
0x1ad02c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ad031  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad036  ldarg.0
0x1ad037  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad03c  ldstr    aCheckpermissio_0// "CheckPermissions"
0x1ad041  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ad046  ldarg.0
0x1ad047  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad04c  ldc.i4.1
0x1ad04d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ad052  ldarg.0
0x1ad053  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad058  ldc.i4.0
0x1ad059  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ad05e  ldarg.0
0x1ad05f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad064  ldc.i4.8
0x1ad065  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ad06a  ldarg.0
0x1ad06b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad070  ldstr    aCheckpermissio_0// "CheckPermissions"
0x1ad075  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ad07a  ldarg.0
0x1ad07b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad080  ldc.i4.0
0x1ad081  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ad086  ldarg.0
0x1ad087  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad08c  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.EntityPermission>
0x1ad091  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad096  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1ad09b  ldarg.0
0x1ad09c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad0a1  ldc.i4.3
0x1ad0a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ad0a7  ldarg.0
0x1ad0a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad0ad  ldc.i4.1
0x1ad0ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1ad0b3  ldarg.0
0x1ad0b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad0b9  ldc.i4.0
0x1ad0ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1ad0bf  ldarg.0
0x1ad0c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad0c5  ldc.i4.0
0x1ad0c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ad0cb  ldarg.0
0x1ad0cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad0d1  ldc.i4.1
0x1ad0d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1ad0d7  ldarg.0
0x1ad0d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal0
0x1ad0dd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<item>5__30
0x1ad0e2  ldarg.0
0x1ad0e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<item>5__30
0x1ad0e8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ad0ed  ldarg.0
0x1ad0ee  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1ad0f3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad0f8  ldarg.0
0x1ad0f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad0fe  ldstr    aListitem// "listItem"
0x1ad103  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ad108  ldarg.0
0x1ad109  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad10e  ldc.i4.0
0x1ad10f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ad114  ldarg.0
0x1ad115  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad11a  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x1ad11f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad124  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ad129  ldarg.0
0x1ad12a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad12f  ldc.i4.0
0x1ad130  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ad135  ldarg.0
0x1ad136  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad13b  ldc.i4.0
0x1ad13c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1ad141  ldarg.0
0x1ad142  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad147  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ad14c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1ad151  ldarg.0
0x1ad152  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal1
0x1ad157  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1ad15c  ldarg.0
0x1ad15d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<item>5__30
0x1ad162  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ad167  ldarg.0
0x1ad168  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1ad16d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad172  ldarg.0
0x1ad173  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad178  ldstr    aRecipients// "recipients"
0x1ad17d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ad182  ldarg.0
0x1ad183  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad188  ldc.i4.0
0x1ad189  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ad18e  ldarg.0
0x1ad18f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad194  ldtoken  class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Recipient[]
0x1ad199  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad19e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ad1a3  ldarg.0
0x1ad1a4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad1a9  ldc.i4.3
0x1ad1aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ad1af  ldarg.0
0x1ad1b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad1b5  ldc.i4.0
0x1ad1b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1ad1bb  ldarg.0
0x1ad1bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad1c1  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ad1c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1ad1cb  ldarg.0
0x1ad1cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal2
0x1ad1d1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1ad1d6  ldarg.0
0x1ad1d7  ldarg.0
0x1ad1d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<item>5__30
0x1ad1dd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>2__current
0x1ad1e2  ldarg.0
0x1ad1e3  ldc.i4.3
0x1ad1e4  stfld    int32 <GetMethods>d__2e::<>1__state
0x1ad1e9  ldc.i4.1
0x1ad1ea  stloc.0
0x1ad1eb  leave    loc_1AE9D4
0x1ad1f0  ldarg.0
0x1ad1f1  ldc.i4.m1
0x1ad1f2  stfld    int32 <GetMethods>d__2e::<>1__state
0x1ad1f7  ldarg.0
0x1ad1f8  ldarg.0
0x1ad1f9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ad1fe  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad203  ldarg.0
0x1ad204  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad209  ldstr    aDeletelinkbyki// "DeleteLinkByKind"
0x1ad20e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ad213  ldarg.0
0x1ad214  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad219  ldc.i4.1
0x1ad21a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ad21f  ldarg.0
0x1ad220  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad225  ldc.i4.0
0x1ad226  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ad22b  ldarg.0
0x1ad22c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad231  ldc.i4.8
0x1ad232  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ad237  ldarg.0
0x1ad238  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad23d  ldstr    aDeletelinkbyki// "DeleteLinkByKind"
0x1ad242  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ad247  ldarg.0
0x1ad248  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad24d  ldc.i4.0
0x1ad24e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ad253  ldarg.0
0x1ad254  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad259  ldtoken  [mscorlib]System.Void
0x1ad25e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad263  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1ad268  ldarg.0
0x1ad269  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad26e  ldc.i4.0
0x1ad26f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ad274  ldarg.0
0x1ad275  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad27a  ldc.i4.1
0x1ad27b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1ad280  ldarg.0
0x1ad281  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad286  ldc.i4.0
0x1ad287  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1ad28c  ldarg.0
0x1ad28d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad292  ldc.i4.0
0x1ad293  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ad298  ldarg.0
0x1ad299  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad29e  ldc.i4.1
0x1ad29f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1ad2a4  ldarg.0
0x1ad2a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<>g__initLocal3
0x1ad2aa  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<item>5__30
0x1ad2af  ldarg.0
0x1ad2b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<item>5__30
0x1ad2b5  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ad2ba  ldarg.0
0x1ad2bb  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1ad2c0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad2c5  ldarg.0
0x1ad2c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad2cb  ldstr    aItem// "item"
0x1ad2d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ad2d5  ldarg.0
0x1ad2d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad2db  ldc.i4.0
0x1ad2dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ad2e1  ldarg.0
0x1ad2e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad2e7  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x1ad2ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad2f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ad2f6  ldarg.0
0x1ad2f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad2fc  ldc.i4.0
0x1ad2fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ad302  ldarg.0
0x1ad303  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad308  ldc.i4.0
0x1ad309  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1ad30e  ldarg.0
0x1ad30f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad314  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ad319  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1ad31e  ldarg.0
0x1ad31f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal4
0x1ad324  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1ad329  ldarg.0
0x1ad32a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2e::<item>5__30
0x1ad32f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ad334  ldarg.0
0x1ad335  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1ad33a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal5
0x1ad33f  ldarg.0
0x1ad340  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal5
0x1ad345  ldstr    aLinkkind_0// "linkKind"
0x1ad34a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ad34f  ldarg.0
0x1ad350  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal5
0x1ad355  ldc.i4.0
0x1ad356  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ad35b  ldarg.0
0x1ad35c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal5
0x1ad361  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind
0x1ad366  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad36b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ad370  ldarg.0
0x1ad371  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2e::<>g__initLocal5
0x1ad376  ldc.i4.1
  ... truncated ...
```
