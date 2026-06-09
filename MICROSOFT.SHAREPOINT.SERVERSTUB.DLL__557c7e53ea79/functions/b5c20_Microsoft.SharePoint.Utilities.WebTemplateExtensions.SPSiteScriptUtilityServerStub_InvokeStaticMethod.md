# Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::InvokeStaticMethod

- ea: `0xb5c20`
- end: `0xb5f3e`
- name: `Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::InvokeStaticMethod`
- size: `798`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xb5a00`
- `0xb5a20`
- `0xb5a40`
- `0xb5a60`
- `0xb5a70`
- `0xb5a90`
- `0xb5ab0`
- `0xb5ad0`
- `0xb5ae0`
- `0xb5af0`
- `0xb5b00`
- `0xb5b40`
- `0xb5b70`
- `0xb5b90`
- `0xb5bb0`
- `0xb5bd0`
- `0xb5bf0`
- `0xb5c20`

## string_xrefs

- `0xb5cb4`: `ValidatePendingWebTemplateExtension`
- `0xb5e58`: `ValidatePendingWebTemplateExtension`
- `0xb5c60`: `CreateSiteScript`
- `0xb5dae`: `CreateSiteScript`
- `0xb5c6c`: `DeleteSiteScript`
- `0xb5dc6`: `DeleteSiteScript`
- `0xb5c90`: `CreateSiteDesign`
- `0xb5e0f`: `CreateSiteDesign`
- `0xb5c9c`: `DeleteSiteDesign`
- `0xb5e27`: `DeleteSiteDesign`
- `0xb5cf4`: `UpdateSiteScript`
- `0xb5edc`: `UpdateSiteScript`
- `0xb5d01`: `UpdateSiteScriptContent`
- `0xb5ef4`: `UpdateSiteScriptContent`
- `0xb5d0e`: `UpdateSiteDesign`
- `0xb5f0c`: `UpdateSiteDesign`

## pseudocode

```c

```

## disassembly

```asm
0xb5c20  ldarg.3
0xb5c21  brtrue.s loc_B5C2E
0xb5c23  ldstr    aProxycontext// "proxyContext"
0xb5c28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb5c2d  throw
0xb5c2e  ldarg.0
0xb5c2f  ldarg.1
0xb5c30  ldarg.3
0xb5c31  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5c36  starg.s  1
0xb5c38  ldarg.1
0xb5c39  dup
0xb5c3a  stloc.0
0xb5c3b  brfalse  loc_B5F37
0xb5c40  volatile.
0xb5c42  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001de3-1
0xb5c47  brtrue   loc_B5D2E
0xb5c4c  ldc.i4.s 0x11
0xb5c4e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb5c53  dup
0xb5c54  ldstr    aGetsitescriptm// "GetSiteScriptMetadata"
0xb5c59  ldc.i4.0
0xb5c5a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5c5f  dup
0xb5c60  ldstr    aCreatesitescri// "CreateSiteScript"
0xb5c65  ldc.i4.1
0xb5c66  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5c6b  dup
0xb5c6c  ldstr    aDeletesitescri// "DeleteSiteScript"
0xb5c71  ldc.i4.2
0xb5c72  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5c77  dup
0xb5c78  ldstr    aGetsitescripts// "GetSiteScripts"
0xb5c7d  ldc.i4.3
0xb5c7e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5c83  dup
0xb5c84  ldstr    aGetsitedesignm// "GetSiteDesignMetadata"
0xb5c89  ldc.i4.4
0xb5c8a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5c8f  dup
0xb5c90  ldstr    aCreatesitedesi// "CreateSiteDesign"
0xb5c95  ldc.i4.5
0xb5c96  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5c9b  dup
0xb5c9c  ldstr    aDeletesitedesi// "DeleteSiteDesign"
0xb5ca1  ldc.i4.6
0xb5ca2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5ca7  dup
0xb5ca8  ldstr    aGetsitedesigns// "GetSiteDesigns"
0xb5cad  ldc.i4.7
0xb5cae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5cb3  dup
0xb5cb4  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb5cb9  ldc.i4.8
0xb5cba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5cbf  dup
0xb5cc0  ldstr    aApplyimplicits// "ApplyImplicitSiteDesign"
0xb5cc5  ldc.i4.s 9
0xb5cc7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5ccc  dup
0xb5ccd  ldstr    aGrantsitedesig// "GrantSiteDesignRights"
0xb5cd2  ldc.i4.s 0xA
0xb5cd4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5cd9  dup
0xb5cda  ldstr    aRevokesitedesi// "RevokeSiteDesignRights"
0xb5cdf  ldc.i4.s 0xB
0xb5ce1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5ce6  dup
0xb5ce7  ldstr    aGetsitedesignr// "GetSiteDesignRights"
0xb5cec  ldc.i4.s 0xC
0xb5cee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5cf3  dup
0xb5cf4  ldstr    aUpdatesitescri// "UpdateSiteScript"
0xb5cf9  ldc.i4.s 0xD
0xb5cfb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5d00  dup
0xb5d01  ldstr    aUpdatesitescri_0// "UpdateSiteScriptContent"
0xb5d06  ldc.i4.s 0xE
0xb5d08  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5d0d  dup
0xb5d0e  ldstr    aUpdatesitedesi// "UpdateSiteDesign"
0xb5d13  ldc.i4.s 0xF
0xb5d15  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5d1a  dup
0xb5d1b  ldstr    aApplysitedesig// "ApplySiteDesign"
0xb5d20  ldc.i4.s 0x10
0xb5d22  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5d27  volatile.
0xb5d29  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001de3-1
0xb5d2e  volatile.
0xb5d30  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001de3-1
0xb5d35  ldloc.0
0xb5d36  ldloca.s 1
0xb5d38  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb5d3d  brfalse  loc_B5F37
0xb5d42  ldloc.1
0xb5d43  switch   loc_B5D91, loc_B5DA9, loc_B5DC1, loc_B5DDA, loc_B5DF2, loc_B5E0A, loc_B5E22, loc_B5E3B, loc_B5E53, loc_B5E70, loc_B5E8D, loc_B5EA6, loc_B5EBF, loc_B5ED7, loc_B5EEF, loc_B5F07, loc_B5F1F
0xb5d8c  br       loc_B5F37
0xb5d91  ldarg.s  4
0xb5d93  ldc.i4.0
0xb5d94  stind.i1
0xb5d95  ldarg.0
0xb5d96  ldstr    aGetsitescriptm// "GetSiteScriptMetadata"
0xb5d9b  ldarg.3
0xb5d9c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5da1  ldarg.2
0xb5da2  ldarg.3
0xb5da3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteScriptMetadata_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5da8  ret
0xb5da9  ldarg.s  4
0xb5dab  ldc.i4.0
0xb5dac  stind.i1
0xb5dad  ldarg.0
0xb5dae  ldstr    aCreatesitescri// "CreateSiteScript"
0xb5db3  ldarg.3
0xb5db4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5db9  ldarg.2
0xb5dba  ldarg.3
0xb5dbb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::CreateSiteScript_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5dc0  ret
0xb5dc1  ldarg.s  4
0xb5dc3  ldc.i4.1
0xb5dc4  stind.i1
0xb5dc5  ldarg.0
0xb5dc6  ldstr    aDeletesitescri// "DeleteSiteScript"
0xb5dcb  ldarg.3
0xb5dcc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5dd1  ldarg.2
0xb5dd2  ldarg.3
0xb5dd3  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::DeleteSiteScript_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5dd8  ldnull
0xb5dd9  ret
0xb5dda  ldarg.s  4
0xb5ddc  ldc.i4.0
0xb5ddd  stind.i1
0xb5dde  ldarg.0
0xb5ddf  ldstr    aGetsitescripts// "GetSiteScripts"
0xb5de4  ldarg.3
0xb5de5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5dea  ldarg.2
0xb5deb  ldarg.3
0xb5dec  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteScripts_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5df1  ret
0xb5df2  ldarg.s  4
0xb5df4  ldc.i4.0
0xb5df5  stind.i1
0xb5df6  ldarg.0
0xb5df7  ldstr    aGetsitedesignm// "GetSiteDesignMetadata"
0xb5dfc  ldarg.3
0xb5dfd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5e02  ldarg.2
0xb5e03  ldarg.3
0xb5e04  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteDesignMetadata_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5e09  ret
0xb5e0a  ldarg.s  4
0xb5e0c  ldc.i4.0
0xb5e0d  stind.i1
0xb5e0e  ldarg.0
0xb5e0f  ldstr    aCreatesitedesi// "CreateSiteDesign"
0xb5e14  ldarg.3
0xb5e15  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5e1a  ldarg.2
0xb5e1b  ldarg.3
0xb5e1c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::CreateSiteDesign_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5e21  ret
0xb5e22  ldarg.s  4
0xb5e24  ldc.i4.1
0xb5e25  stind.i1
0xb5e26  ldarg.0
0xb5e27  ldstr    aDeletesitedesi// "DeleteSiteDesign"
0xb5e2c  ldarg.3
0xb5e2d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5e32  ldarg.2
0xb5e33  ldarg.3
0xb5e34  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::DeleteSiteDesign_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5e39  ldnull
0xb5e3a  ret
0xb5e3b  ldarg.s  4
0xb5e3d  ldc.i4.0
0xb5e3e  stind.i1
0xb5e3f  ldarg.0
0xb5e40  ldstr    aGetsitedesigns// "GetSiteDesigns"
0xb5e45  ldarg.3
0xb5e46  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5e4b  ldarg.2
0xb5e4c  ldarg.3
0xb5e4d  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteDesigns_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5e52  ret
0xb5e53  ldarg.s  4
0xb5e55  ldc.i4.0
0xb5e56  stind.i1
0xb5e57  ldarg.0
0xb5e58  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb5e5d  ldarg.3
0xb5e5e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5e63  ldarg.2
0xb5e64  ldarg.3
0xb5e65  call     bool Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::ValidatePendingWebTemplateExtension_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5e6a  box      [mscorlib]System.Boolean
0xb5e6f  ret
0xb5e70  ldarg.s  4
0xb5e72  ldc.i4.0
0xb5e73  stind.i1
0xb5e74  ldarg.0
0xb5e75  ldstr    aApplyimplicits// "ApplyImplicitSiteDesign"
0xb5e7a  ldarg.3
0xb5e7b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5e80  ldarg.2
0xb5e81  ldarg.3
0xb5e82  call     bool Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::ApplyImplicitSiteDesign_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5e87  box      [mscorlib]System.Boolean
0xb5e8c  ret
0xb5e8d  ldarg.s  4
0xb5e8f  ldc.i4.1
0xb5e90  stind.i1
0xb5e91  ldarg.0
0xb5e92  ldstr    aGrantsitedesig// "GrantSiteDesignRights"
0xb5e97  ldarg.3
0xb5e98  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5e9d  ldarg.2
0xb5e9e  ldarg.3
0xb5e9f  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GrantSiteDesignRights_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5ea4  ldnull
0xb5ea5  ret
0xb5ea6  ldarg.s  4
0xb5ea8  ldc.i4.1
0xb5ea9  stind.i1
0xb5eaa  ldarg.0
0xb5eab  ldstr    aRevokesitedesi// "RevokeSiteDesignRights"
0xb5eb0  ldarg.3
0xb5eb1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5eb6  ldarg.2
0xb5eb7  ldarg.3
0xb5eb8  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::RevokeSiteDesignRights_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5ebd  ldnull
0xb5ebe  ret
0xb5ebf  ldarg.s  4
0xb5ec1  ldc.i4.0
0xb5ec2  stind.i1
0xb5ec3  ldarg.0
0xb5ec4  ldstr    aGetsitedesignr// "GetSiteDesignRights"
0xb5ec9  ldarg.3
0xb5eca  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5ecf  ldarg.2
0xb5ed0  ldarg.3
0xb5ed1  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignPrincipal> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteDesignRights_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5ed6  ret
0xb5ed7  ldarg.s  4
0xb5ed9  ldc.i4.0
0xb5eda  stind.i1
0xb5edb  ldarg.0
0xb5edc  ldstr    aUpdatesitescri// "UpdateSiteScript"
0xb5ee1  ldarg.3
0xb5ee2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5ee7  ldarg.2
0xb5ee8  ldarg.3
0xb5ee9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::UpdateSiteScript_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5eee  ret
0xb5eef  ldarg.s  4
0xb5ef1  ldc.i4.0
0xb5ef2  stind.i1
0xb5ef3  ldarg.0
0xb5ef4  ldstr    aUpdatesitescri_0// "UpdateSiteScriptContent"
0xb5ef9  ldarg.3
0xb5efa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5eff  ldarg.2
0xb5f00  ldarg.3
0xb5f01  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::UpdateSiteScriptContent_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5f06  ret
0xb5f07  ldarg.s  4
0xb5f09  ldc.i4.0
0xb5f0a  stind.i1
0xb5f0b  ldarg.0
0xb5f0c  ldstr    aUpdatesitedesi// "UpdateSiteDesign"
0xb5f11  ldarg.3
0xb5f12  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5f17  ldarg.2
0xb5f18  ldarg.3
0xb5f19  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::UpdateSiteDesign_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5f1e  ret
0xb5f1f  ldarg.s  4
0xb5f21  ldc.i4.0
0xb5f22  stind.i1
0xb5f23  ldarg.0
0xb5f24  ldstr    aApplysitedesig// "ApplySiteDesign"
0xb5f29  ldarg.3
0xb5f2a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5f2f  ldarg.2
0xb5f30  ldarg.3
0xb5f31  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptActionResult> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::ApplySiteDesign_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5f36  ret
0xb5f37  ldarg.1
0xb5f38  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb5f3d  throw
```
