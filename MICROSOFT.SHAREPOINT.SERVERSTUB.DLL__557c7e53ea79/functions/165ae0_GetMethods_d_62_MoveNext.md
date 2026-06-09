# <GetMethods>d__62::MoveNext

- ea: `0x165ae0`
- end: `0x169a5b`
- name: `<GetMethods>d__62::MoveNext`
- size: `16251`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x84240`
- `0x165ae0`
- `0x169a80`
- `0x169ae0`

## string_xrefs

- `0x1690ec`: `RestUpdate`
- `0x169121`: `RestUpdate`
- `0x169012`: `RemoveHubSite`
- `0x169046`: `RemoveHubSite`
- `0x16990b`: `UpdateClientObjectModelUseRemoteAPIsPermissionSetting`
- `0x169943`: `UpdateClientObjectModelUseRemoteAPIsPermissionSetting`
- `0x166a0d`: `CreatePreviewSPSite`
- `0x166a45`: `CreatePreviewSPSite`
- `0x166bde`: `DeleteMigrationJob`
- `0x166c16`: `DeleteMigrationJob`
- `0x166409`: `CreateMigrationJob`
- `0x166441`: `CreateMigrationJob`
- `0x1666ce`: `CreateMigrationJobEncrypted`
- `0x166706`: `CreateMigrationJobEncrypted`
- `0x1660ca`: `CreateMigrationIngestionJob`
- `0x166102`: `CreateMigrationIngestionJob`
- `0x1682aa`: `MultiGeoCopyJob`
- `0x1682de`: `MultiGeoCopyJob`
- `0x165c34`: `CreateCopyJob`
- `0x165c6c`: `CreateCopyJob`
- `0x165e7f`: `CreateCopyJobs`
- `0x165eb7`: `CreateCopyJobs`
- `0x1673d8`: `GetCopyJobProgress`
- `0x167410`: `GetCopyJobProgress`
- `0x16881c`: `OpenWeb`
- `0x168854`: `OpenWeb`
- `0x1689ac`: `OpenWeb`
- `0x168b04`: `OpenWeb`
- `0x168acc`: `OpenWebUsingPath`
- `0x168974`: `OpenWebById`
- `0x167bfa`: `GetWebPath`
- `0x167c32`: `GetWebPath`
- `0x167dcc`: `GetWebTemplates`
- `0x167e04`: `GetWebTemplates`
- `0x167530`: `GetCustomListTemplates`
- `0x167564`: `GetCustomListTemplates`
- `0x165cfa`: `exportObjectUris`
- `0x165f45`: `exportObjectUris`
- `0x165d74`: `destinationUri`
- `0x165fbf`: `destinationUri`
- `0x16620a`: `azureContainerSourceUri`
- `0x166549`: `azureContainerSourceUri`
- `0x16680e`: `azureContainerSourceUri`
- `0x166284`: `azureContainerManifestUri`
- `0x1665c3`: `azureContainerManifestUri`
- `0x166888`: `azureContainerManifestUri`
- `0x1662fe`: `azureQueueReportUri`
- `0x16663d`: `azureQueueReportUri`
- `0x166902`: `azureQueueReportUri`
- `0x166378`: `ingestionTaskKey`
- `0x16749e`: `copyJobInfo`
- `0x167f0c`: `overrideCompatLevel`
- `0x1694d9`: `bRepair`

## pseudocode

```c

```

## disassembly

```asm
0x165ae0  ldarg.0
0x165ae1  ldfld    int32 <GetMethods>d__62::<>1__state
0x165ae6  stloc.1
0x165ae7  ldloc.1
0x165ae8  switch   loc_165B9E, loc_169A4E, loc_165C08, loc_165E66, loc_1660B1, loc_1663F0, loc_1666B5, loc_1669F4, loc_166BC5, loc_166D1D, loc_166E75, loc_166F53, loc_167031, loc_16710F, loc_167267, loc_1673BF, loc_167517, loc_16766B, loc_1677C3, loc_1678A1, loc_167BE1, loc_167DB3, loc_167F85, loc_168063, loc_1681B7, loc_168291, loc_1684D9, loc_1686AB, loc_168803, loc_16895B, loc_168AB3, loc_168C0B, loc_168CE9, loc_168DC7, loc_168F1F, loc_168FF9, loc_1690D3, loc_1691AE, loc_169380, loc_1695CC, loc_169818, loc_1698F2, loc_169A47
0x165b99  br       loc_169A4E
0x165b9e  ldarg.0
0x165b9f  ldc.i4.m1
0x165ba0  stfld    int32 <GetMethods>d__62::<>1__state
0x165ba5  ldarg.0
0x165ba6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__62::proxyContext
0x165bab  brtrue.s loc_165BB8
0x165bad  ldstr    aProxycontext// "proxyContext"
0x165bb2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x165bb7  throw
0x165bb8  ldarg.0
0x165bb9  ldarg.0
0x165bba  ldfld    class Microsoft.SharePoint.ServerStub.SPSiteServerStub <GetMethods>d__62::<>4__this
0x165bbf  ldarg.0
0x165bc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__62::proxyContext
0x165bc5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPSiteServerStub::<>n__FabricatedMethod67(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x165bca  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x165bcf  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__62::<>7__wrap65
0x165bd4  ldarg.0
0x165bd5  ldc.i4.1
0x165bd6  stfld    int32 <GetMethods>d__62::<>1__state
0x165bdb  br.s     loc_165C0F
0x165bdd  ldarg.0
0x165bde  ldarg.0
0x165bdf  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__62::<>7__wrap65
0x165be4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x165be9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<itemBase>5__63
0x165bee  ldarg.0
0x165bef  ldarg.0
0x165bf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<itemBase>5__63
0x165bf5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>2__current
0x165bfa  ldarg.0
0x165bfb  ldc.i4.2
0x165bfc  stfld    int32 <GetMethods>d__62::<>1__state
0x165c01  ldc.i4.1
0x165c02  stloc.0
0x165c03  leave    loc_169A59
0x165c08  ldarg.0
0x165c09  ldc.i4.1
0x165c0a  stfld    int32 <GetMethods>d__62::<>1__state
0x165c0f  ldarg.0
0x165c10  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__62::<>7__wrap65
0x165c15  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x165c1a  brtrue.s loc_165BDD
0x165c1c  ldarg.0
0x165c1d  call     instance void <GetMethods>d__62::<>m__Finally66()
0x165c22  ldarg.0
0x165c23  ldarg.0
0x165c24  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x165c29  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c2e  ldarg.0
0x165c2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c34  ldstr    aCreatecopyjob// "CreateCopyJob"
0x165c39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x165c3e  ldarg.0
0x165c3f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c44  ldc.i4.0
0x165c45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x165c4a  ldarg.0
0x165c4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c50  ldc.i4.0
0x165c51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x165c56  ldarg.0
0x165c57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c5c  ldc.i4   0xFFFFFFF
0x165c61  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x165c66  ldarg.0
0x165c67  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c6c  ldstr    aCreatecopyjob// "CreateCopyJob"
0x165c71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x165c76  ldarg.0
0x165c77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c7c  ldc.i4.0
0x165c7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x165c82  ldarg.0
0x165c83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c88  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPCopyMigrationInfo
0x165c8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x165c92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x165c97  ldarg.0
0x165c98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165c9d  ldc.i4.2
0x165c9e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x165ca3  ldarg.0
0x165ca4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165ca9  ldc.i4.0
0x165caa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x165caf  ldarg.0
0x165cb0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165cb5  ldc.i4.0
0x165cb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x165cbb  ldarg.0
0x165cbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165cc1  ldc.i4.0
0x165cc2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x165cc7  ldarg.0
0x165cc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165ccd  ldc.i4.0
0x165cce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x165cd3  ldarg.0
0x165cd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal0
0x165cd9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<item>5__64
0x165cde  ldarg.0
0x165cdf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<item>5__64
0x165ce4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x165ce9  ldarg.0
0x165cea  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x165cef  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165cf4  ldarg.0
0x165cf5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165cfa  ldstr    aExportobjectur// "exportObjectUris"
0x165cff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x165d04  ldarg.0
0x165d05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165d0a  ldc.i4.0
0x165d0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x165d10  ldarg.0
0x165d11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165d16  ldtoken  class [System]System.Uri[]
0x165d1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x165d20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x165d25  ldarg.0
0x165d26  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165d2b  ldc.i4.3
0x165d2c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x165d31  ldarg.0
0x165d32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165d37  ldc.i4.0
0x165d38  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x165d3d  ldarg.0
0x165d3e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165d43  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x165d48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x165d4d  ldarg.0
0x165d4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal1
0x165d53  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x165d58  ldarg.0
0x165d59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<item>5__64
0x165d5e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x165d63  ldarg.0
0x165d64  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x165d69  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165d6e  ldarg.0
0x165d6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165d74  ldstr    aDestinationuri// "destinationUri"
0x165d79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x165d7e  ldarg.0
0x165d7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165d84  ldc.i4.0
0x165d85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x165d8a  ldarg.0
0x165d8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165d90  ldtoken  [System]System.Uri
0x165d95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x165d9a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x165d9f  ldarg.0
0x165da0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165da5  ldc.i4.1
0x165da6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x165dab  ldarg.0
0x165dac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165db1  ldc.i4.0
0x165db2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x165db7  ldarg.0
0x165db8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165dbd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x165dc2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x165dc7  ldarg.0
0x165dc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal2
0x165dcd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x165dd2  ldarg.0
0x165dd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<item>5__64
0x165dd8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x165ddd  ldarg.0
0x165dde  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x165de3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165de8  ldarg.0
0x165de9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165dee  ldstr    aOptions// "options"
0x165df3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x165df8  ldarg.0
0x165df9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165dfe  ldc.i4.0
0x165dff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x165e04  ldarg.0
0x165e05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165e0a  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPCopyMigrationOptions
0x165e0f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x165e14  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x165e19  ldarg.0
0x165e1a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165e1f  ldc.i4.2
0x165e20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x165e25  ldarg.0
0x165e26  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165e2b  ldc.i4.0
0x165e2c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x165e31  ldarg.0
0x165e32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165e37  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x165e3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x165e41  ldarg.0
0x165e42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal3
0x165e47  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x165e4c  ldarg.0
0x165e4d  ldarg.0
0x165e4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<item>5__64
0x165e53  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>2__current
0x165e58  ldarg.0
0x165e59  ldc.i4.3
0x165e5a  stfld    int32 <GetMethods>d__62::<>1__state
0x165e5f  ldc.i4.1
0x165e60  stloc.0
0x165e61  leave    loc_169A59
0x165e66  ldarg.0
0x165e67  ldc.i4.m1
0x165e68  stfld    int32 <GetMethods>d__62::<>1__state
0x165e6d  ldarg.0
0x165e6e  ldarg.0
0x165e6f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x165e74  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165e79  ldarg.0
0x165e7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165e7f  ldstr    aCreatecopyjobs// "CreateCopyJobs"
0x165e84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x165e89  ldarg.0
0x165e8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165e8f  ldc.i4.0
0x165e90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x165e95  ldarg.0
0x165e96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165e9b  ldc.i4.0
0x165e9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x165ea1  ldarg.0
0x165ea2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165ea7  ldc.i4   0xFFFFFFF
0x165eac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x165eb1  ldarg.0
0x165eb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165eb7  ldstr    aCreatecopyjobs// "CreateCopyJobs"
0x165ebc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x165ec1  ldarg.0
0x165ec2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165ec7  ldc.i4.0
0x165ec8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x165ecd  ldarg.0
0x165ece  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165ed3  ldtoken  class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPCopyMigrationInfo>
0x165ed8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x165edd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x165ee2  ldarg.0
0x165ee3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165ee8  ldc.i4.3
0x165ee9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x165eee  ldarg.0
0x165eef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165ef4  ldc.i4.0
0x165ef5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x165efa  ldarg.0
0x165efb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165f00  ldc.i4.0
0x165f01  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x165f06  ldarg.0
0x165f07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165f0c  ldc.i4.0
0x165f0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x165f12  ldarg.0
0x165f13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165f18  ldc.i4.0
0x165f19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x165f1e  ldarg.0
0x165f1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<>g__initLocal4
0x165f24  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<item>5__64
0x165f29  ldarg.0
0x165f2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__62::<item>5__64
0x165f2f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x165f34  ldarg.0
0x165f35  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x165f3a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal5
0x165f3f  ldarg.0
0x165f40  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal5
0x165f45  ldstr    aExportobjectur// "exportObjectUris"
0x165f4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x165f4f  ldarg.0
0x165f50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal5
0x165f55  ldc.i4.0
0x165f56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x165f5b  ldarg.0
0x165f5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal5
0x165f61  ldtoken  class [System]System.Uri[]
0x165f66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x165f6b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x165f70  ldarg.0
0x165f71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__62::<>g__initLocal5
0x165f76  ldc.i4.3
  ... truncated ...
```
