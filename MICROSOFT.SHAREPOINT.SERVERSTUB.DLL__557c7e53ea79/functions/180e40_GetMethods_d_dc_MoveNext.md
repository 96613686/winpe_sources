# <GetMethods>d__dc::MoveNext

- ea: `0x180e40`
- end: `0x189c6c`
- name: `<GetMethods>d__dc::MoveNext`
- size: `36396`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x9b900`
- `0x180e40`
- `0x189c90`
- `0x189cf0`

## string_xrefs

- `0x181699`: `copyRoleAssignments`
- `0x189b96`: `Update`
- `0x189bce`: `Update`
- `0x1825b8`: `DeleteObject`
- `0x1825f0`: `Delete`
- `0x184e61`: `serverRelativePath`
- `0x1858b5`: `serverRelativePath`
- `0x1891d8`: `comments`
- `0x184d9b`: `GetFileByServerRelativePath`
- `0x18401d`: `GetCustomListTemplates`
- `0x184051`: `GetCustomListTemplates`
- `0x181bc0`: `CreateDefaultAssociatedGroups`
- `0x181bf8`: `CreateDefaultAssociatedGroups`
- `0x183bc0`: `GetClientSideComponentsById`
- `0x183bf4`: `GetClientSideComponentsById`
- `0x183a6c`: `GetClientSideComponents`
- `0x183aa0`: `GetClientSideComponents`
- `0x183d14`: `GetClientSideWebParts`
- `0x183d48`: `GetClientSideWebParts`
- `0x188c16`: `RemoveStorageEntity`
- `0x188c4e`: `RemoveStorageEntity`
- `0x186f4f`: `GetSharingLinkData`
- `0x186f87`: `GetSharingLinkData`
- `0x1835ea`: `GetAvailableWebTemplates`
- `0x183622`: `GetAvailableWebTemplates`
- `0x184c43`: `GetFileByLinkingUrl`
- `0x184c7b`: `GetFileByLinkingUrl`
- `0x18474b`: `GetFileByGuestUrlEnsureAccess`
- `0x1857ef`: `GetFolderByServerRelativePath`
- `0x185fff`: `GetListUsingPath`
- `0x185ea7`: `GetListItemUsingPath`
- `0x18147c`: `ApplyWebTemplate`
- `0x1814b4`: `ApplyWebTemplate`
- `0x187929`: `GetViewFromPath`
- `0x187961`: `GetViewFromPath`
- `0x1880b8`: `LoadAndInstallAppInSpecifiedLocale`
- `0x1880f0`: `LoadAndInstallAppInSpecifiedLocale`
- `0x187f60`: `LoadAndInstallApp`
- `0x187f98`: `LoadAndInstallApp`
- `0x188d6e`: `RemoveSupportedUILanguage`
- `0x182e3e`: `ForwardObjectLink`
- `0x182e76`: `ForwardObjectLink`
- `0x1817a4`: `CreateAnonymousLink`
- `0x1817dc`: `CreateAnonymousLink`
- `0x1819ad`: `CreateAnonymousLink`
- `0x181975`: `CreateAnonymousLinkWithExpiration`
- `0x182214`: `DeleteAllAnonymousLinksForObject`
- `0x18224c`: `DeleteAllAnonymousLinksForObject`
- `0x18236c`: `DeleteAnonymousLinkForObject`
- `0x1823a4`: `DeleteAnonymousLinkForObject`
- `0x181e0c`: `CreateOrganizationSharingLink`
- `0x181e44`: `CreateOrganizationSharingLink`
- `0x182696`: `DestroyOrganizationSharingLink`
- `0x1826ce`: `DestroyOrganizationSharingLink`
- `0x1870a7`: `GetSharingLinkKind`
- `0x1870df`: `GetSharingLinkKind`
- `0x181542`: `webTemplate`
- `0x1818e4`: `isEditLink`
- `0x181ab5`: `isEditLink`
- `0x181f4c`: `isEditLink`
- `0x1824ac`: `isEditLink`
- `0x1827d6`: `isEditLink`
- `0x182526`: `removeAssociatedSharingLinkGroup`
- `0x182850`: `removeAssociatedSharingLinkGroup`
- `0x183b2e`: `components`
- `0x183c82`: `componentIds`
- `0x18488b`: `ensureAccess`
- `0x185437`: `ensureAccess`
- `0x184d09`: `linkingUrl`
- `0x184dd3`: `GetFileByServerRelativePath_Client`
- `0x185827`: `GetFolderByServerRelativePath_Client`
- `0x186219`: `allowCreate`
- `0x187015`: `linkUrl`
- `0x187419`: `nWebTemplateFilter`
- `0x187493`: `nConfigurationFilter`
- `0x1879ef`: `listPath`
- `0x1881f8`: `installationLocaleLCID`
- `0x1883ca`: `installationLocaleLCID`
- `0x188b84`: `serviceToken`
- `0x188da6`: `RemoveSupportedUILanguage_Client`
- `0x189518`: `propagateAcl`
- `0x18960c`: `includeAnonymousLinkInEmail`

## pseudocode

```c

```

## disassembly

```asm
0x180e40  ldarg.0
0x180e41  ldfld    int32 <GetMethods>d__dc::<>1__state
0x180e46  stloc.1
0x180e47  ldloc.1
0x180e48  switch   loc_180FCA, loc_189C5F, loc_181034, loc_18119E, loc_181463, loc_1815BA, loc_18178B, loc_18195C, loc_181BA7, loc_181DF3, loc_181FC5, loc_1820A3, loc_1821FB, loc_182353, loc_18259F, loc_18267D, loc_1828C9, loc_182A21, loc_182B79, loc_182CD1, loc_182E25, loc_1830EB, loc_1831C9, loc_183321, loc_183479, loc_1835D1, loc_1837A3, loc_1838FB, loc_183A53, loc_183BA7, loc_183CFB, loc_183E50, loc_183F2A, loc_184004, loc_1840DE, loc_1842B0, loc_184408, loc_1845DA, loc_184732, loc_184904, loc_184AD2, loc_184C2A, loc_184D82, loc_184EDA, loc_185032, loc_18518A, loc_1852E2, loc_1854B0, loc_18567E, loc_1857D6, loc_18592E, loc_185A86, loc_185BDE \
0x180fc5  br       loc_189C5F
0x180fca  ldarg.0
0x180fcb  ldc.i4.m1
0x180fcc  stfld    int32 <GetMethods>d__dc::<>1__state
0x180fd1  ldarg.0
0x180fd2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__dc::proxyContext
0x180fd7  brtrue.s loc_180FE4
0x180fd9  ldstr    aProxycontext// "proxyContext"
0x180fde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x180fe3  throw
0x180fe4  ldarg.0
0x180fe5  ldarg.0
0x180fe6  ldfld    class Microsoft.SharePoint.ServerStub.SPWebServerStub <GetMethods>d__dc::<>4__this
0x180feb  ldarg.0
0x180fec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__dc::proxyContext
0x180ff1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPWebServerStub::<>n__FabricatedMethode1(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x180ff6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x180ffb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__dc::<>7__wrapdf
0x181000  ldarg.0
0x181001  ldc.i4.1
0x181002  stfld    int32 <GetMethods>d__dc::<>1__state
0x181007  br.s     loc_18103B
0x181009  ldarg.0
0x18100a  ldarg.0
0x18100b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__dc::<>7__wrapdf
0x181010  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x181015  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<itemBase>5__dd
0x18101a  ldarg.0
0x18101b  ldarg.0
0x18101c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<itemBase>5__dd
0x181021  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>2__current
0x181026  ldarg.0
0x181027  ldc.i4.2
0x181028  stfld    int32 <GetMethods>d__dc::<>1__state
0x18102d  ldc.i4.1
0x18102e  stloc.0
0x18102f  leave    loc_189C6A
0x181034  ldarg.0
0x181035  ldc.i4.1
0x181036  stfld    int32 <GetMethods>d__dc::<>1__state
0x18103b  ldarg.0
0x18103c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__dc::<>7__wrapdf
0x181041  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x181046  brtrue.s loc_181009
0x181048  ldarg.0
0x181049  call     instance void <GetMethods>d__dc::<>m__Finallye0()
0x18104e  ldarg.0
0x18104f  ldarg.0
0x181050  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x181055  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x18105a  ldarg.0
0x18105b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x181060  ldstr    aAddsupportedui// "AddSupportedUILanguage"
0x181065  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x18106a  ldarg.0
0x18106b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x181070  ldc.i4.0
0x181071  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x181076  ldarg.0
0x181077  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x18107c  ldc.i4.0
0x18107d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x181082  ldarg.0
0x181083  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x181088  ldc.i4   0xFFFFFFF
0x18108d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x181092  ldarg.0
0x181093  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x181098  ldstr    aAddsupportedui_0// "AddSupportedUILanguage_Client"
0x18109d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1810a2  ldarg.0
0x1810a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x1810a8  ldc.i4.0
0x1810a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1810ae  ldarg.0
0x1810af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x1810b4  ldtoken  [mscorlib]System.Void
0x1810b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1810be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1810c3  ldarg.0
0x1810c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x1810c9  ldc.i4.0
0x1810ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1810cf  ldarg.0
0x1810d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x1810d5  ldc.i4.0
0x1810d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1810db  ldarg.0
0x1810dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x1810e1  ldc.i4.0
0x1810e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1810e7  ldarg.0
0x1810e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x1810ed  ldc.i4.0
0x1810ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1810f3  ldarg.0
0x1810f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x1810f9  ldc.i4.0
0x1810fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1810ff  ldarg.0
0x181100  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal0
0x181105  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<item>5__de
0x18110a  ldarg.0
0x18110b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<item>5__de
0x181110  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x181115  ldarg.0
0x181116  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x18111b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x181120  ldarg.0
0x181121  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x181126  ldstr    aLcid_1// "lcid"
0x18112b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x181130  ldarg.0
0x181131  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x181136  ldc.i4.0
0x181137  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x18113c  ldarg.0
0x18113d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x181142  ldtoken  [mscorlib]System.Int32
0x181147  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18114c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x181151  ldarg.0
0x181152  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x181157  ldc.i4.1
0x181158  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18115d  ldarg.0
0x18115e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x181163  ldc.i4.0
0x181164  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x181169  ldarg.0
0x18116a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x18116f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x181174  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x181179  ldarg.0
0x18117a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal1
0x18117f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x181184  ldarg.0
0x181185  ldarg.0
0x181186  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<item>5__de
0x18118b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>2__current
0x181190  ldarg.0
0x181191  ldc.i4.3
0x181192  stfld    int32 <GetMethods>d__dc::<>1__state
0x181197  ldc.i4.1
0x181198  stloc.0
0x181199  leave    loc_189C6A
0x18119e  ldarg.0
0x18119f  ldc.i4.m1
0x1811a0  stfld    int32 <GetMethods>d__dc::<>1__state
0x1811a5  ldarg.0
0x1811a6  ldarg.0
0x1811a7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1811ac  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x1811b1  ldarg.0
0x1811b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x1811b7  ldstr    aApplytheme// "ApplyTheme"
0x1811bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1811c1  ldarg.0
0x1811c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x1811c7  ldc.i4.0
0x1811c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1811cd  ldarg.0
0x1811ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x1811d3  ldc.i4.0
0x1811d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1811d9  ldarg.0
0x1811da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x1811df  ldc.i4   0xFFFFFFF
0x1811e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1811e9  ldarg.0
0x1811ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x1811ef  ldstr    aApplytheme// "ApplyTheme"
0x1811f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1811f9  ldarg.0
0x1811fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x1811ff  ldc.i4.0
0x181200  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x181205  ldarg.0
0x181206  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x18120b  ldtoken  [mscorlib]System.Void
0x181210  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x181215  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x18121a  ldarg.0
0x18121b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x181220  ldc.i4.0
0x181221  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x181226  ldarg.0
0x181227  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x18122c  ldc.i4.0
0x18122d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x181232  ldarg.0
0x181233  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x181238  ldc.i4.0
0x181239  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x18123e  ldarg.0
0x18123f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x181244  ldc.i4.0
0x181245  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x18124a  ldarg.0
0x18124b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x181250  ldc.i4.0
0x181251  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x181256  ldarg.0
0x181257  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<>g__initLocal2
0x18125c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<item>5__de
0x181261  ldarg.0
0x181262  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<item>5__de
0x181267  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x18126c  ldarg.0
0x18126d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x181272  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x181277  ldarg.0
0x181278  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x18127d  ldstr    aColorpaletteur// "colorPaletteUrl"
0x181282  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x181287  ldarg.0
0x181288  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x18128d  ldc.i4.0
0x18128e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x181293  ldarg.0
0x181294  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x181299  ldtoken  [mscorlib]System.String
0x18129e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1812a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1812a8  ldarg.0
0x1812a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x1812ae  ldc.i4.1
0x1812af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1812b4  ldarg.0
0x1812b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x1812ba  ldc.i4.0
0x1812bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1812c0  ldarg.0
0x1812c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x1812c6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1812cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1812d0  ldarg.0
0x1812d1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal3
0x1812d6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1812db  ldarg.0
0x1812dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<item>5__de
0x1812e1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1812e6  ldarg.0
0x1812e7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1812ec  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x1812f1  ldarg.0
0x1812f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x1812f7  ldstr    aFontschemeurl// "fontSchemeUrl"
0x1812fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x181301  ldarg.0
0x181302  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x181307  ldc.i4.0
0x181308  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x18130d  ldarg.0
0x18130e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x181313  ldtoken  [mscorlib]System.String
0x181318  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18131d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x181322  ldarg.0
0x181323  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x181328  ldc.i4.1
0x181329  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x18132e  ldarg.0
0x18132f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x181334  ldc.i4.0
0x181335  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x18133a  ldarg.0
0x18133b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x181340  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x181345  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x18134a  ldarg.0
0x18134b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal4
0x181350  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x181355  ldarg.0
0x181356  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__dc::<item>5__de
0x18135b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x181360  ldarg.0
0x181361  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x181366  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal5
0x18136b  ldarg.0
0x18136c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal5
0x181371  ldstr    aBackgroundimag// "backgroundImageUrl"
0x181376  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x18137b  ldarg.0
0x18137c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal5
0x181381  ldc.i4.0
0x181382  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x181387  ldarg.0
0x181388  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal5
0x18138d  ldtoken  [mscorlib]System.String
0x181392  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x181397  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x18139c  ldarg.0
0x18139d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__dc::<>g__initLocal5
0x1813a2  ldc.i4.1
  ... truncated ...
```
