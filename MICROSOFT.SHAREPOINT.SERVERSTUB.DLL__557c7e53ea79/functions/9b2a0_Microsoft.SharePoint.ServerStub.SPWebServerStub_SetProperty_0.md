# Microsoft.SharePoint.ServerStub.SPWebServerStub::SetProperty_0

- ea: `0x9b2a0`
- end: `0x9b8ac`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::SetProperty_0`
- size: `1548`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9b2a0`

## string_xrefs

- `0x9b335`: `CommentsOnSitePagesDisabled`
- `0x9b5c9`: `CommentsOnSitePagesDisabled`
- `0x9b490`: `UIVersionConfigurationEnabled`
- `0x9b887`: `UIVersionConfigurationEnabled`
- `0x9b3f4`: `OverwriteTranslationsOnChange`
- `0x9b74f`: `OverwriteTranslationsOnChange`
- `0x9b40e`: `RequestAccessEmail`
- `0x9b783`: `RequestAccessEmail`
- `0x9b41b`: `SaveSiteAsTemplateEnabled`
- `0x9b79d`: `SaveSiteAsTemplateEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x9b2a0  ldarg.s  4
0x9b2a2  brtrue.s loc_9B2AF
0x9b2a4  ldstr    aProxycontext// "proxyContext"
0x9b2a9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9b2ae  throw
0x9b2af  ldarg.1
0x9b2b0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x9b2b5  stloc.0
0x9b2b6  ldloc.0
0x9b2b7  brtrue.s loc_9B2C4
0x9b2b9  ldstr    aTarget// "target"
0x9b2be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9b2c3  throw
0x9b2c4  ldarg.2
0x9b2c5  brtrue.s loc_9B2D2
0x9b2c7  ldstr    aPropname// "propName"
0x9b2cc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9b2d1  throw
0x9b2d2  ldarg.0
0x9b2d3  ldarg.2
0x9b2d4  ldarg.s  4
0x9b2d6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b2db  starg.s  2
0x9b2dd  ldarg.2
0x9b2de  dup
0x9b2df  stloc.1
0x9b2e0  brfalse  loc_9B8A0
0x9b2e5  volatile.
0x9b2e7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600191e-1
0x9b2ec  brtrue   loc_9B4A3
0x9b2f1  ldc.i4.s 0x21
0x9b2f3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x9b2f8  dup
0x9b2f9  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x9b2fe  ldc.i4.0
0x9b2ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b304  dup
0x9b305  ldstr    aAlternatecssur// "AlternateCssUrl"
0x9b30a  ldc.i4.1
0x9b30b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b310  dup
0x9b311  ldstr    aAssociatedmemb// "AssociatedMemberGroup"
0x9b316  ldc.i4.2
0x9b317  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b31c  dup
0x9b31d  ldstr    aAssociatedowne// "AssociatedOwnerGroup"
0x9b322  ldc.i4.3
0x9b323  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b328  dup
0x9b329  ldstr    aAssociatedvisi// "AssociatedVisitorGroup"
0x9b32e  ldc.i4.4
0x9b32f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b334  dup
0x9b335  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x9b33a  ldc.i4.5
0x9b33b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b340  dup
0x9b341  ldstr    aContainsconfid// "ContainsConfidentialInfo"
0x9b346  ldc.i4.6
0x9b347  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b34c  dup
0x9b34d  ldstr    aCustommasterur// "CustomMasterUrl"
0x9b352  ldc.i4.7
0x9b353  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b358  dup
0x9b359  ldstr    aDescription// "Description"
0x9b35e  ldc.i4.8
0x9b35f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b364  dup
0x9b365  ldstr    aDesignpackagei// "DesignPackageId"
0x9b36a  ldc.i4.s 9
0x9b36c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b371  dup
0x9b372  ldstr    aDisableappview// "DisableAppViews"
0x9b377  ldc.i4.s 0xA
0x9b379  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b37e  dup
0x9b37f  ldstr    aDisableflows// "DisableFlows"
0x9b384  ldc.i4.s 0xB
0x9b386  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b38b  dup
0x9b38c  ldstr    aEnableminimald// "EnableMinimalDownload"
0x9b391  ldc.i4.s 0xC
0x9b393  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b398  dup
0x9b399  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x9b39e  ldc.i4.s 0xD
0x9b3a0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3a5  dup
0x9b3a6  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x9b3ab  ldc.i4.s 0xE
0x9b3ad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3b2  dup
0x9b3b3  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x9b3b8  ldc.i4.s 0xF
0x9b3ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3bf  dup
0x9b3c0  ldstr    aIsmultilingual// "IsMultilingual"
0x9b3c5  ldc.i4.s 0x10
0x9b3c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3cc  dup
0x9b3cd  ldstr    aMasterurl// "MasterUrl"
0x9b3d2  ldc.i4.s 0x11
0x9b3d4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3d9  dup
0x9b3da  ldstr    aMemberscanshar// "MembersCanShare"
0x9b3df  ldc.i4.s 0x12
0x9b3e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3e6  dup
0x9b3e7  ldstr    aNocrawl// "NoCrawl"
0x9b3ec  ldc.i4.s 0x13
0x9b3ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3f3  dup
0x9b3f4  ldstr    aOverwritetrans// "OverwriteTranslationsOnChange"
0x9b3f9  ldc.i4.s 0x14
0x9b3fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b400  dup
0x9b401  ldstr    aQuicklaunchena// "QuickLaunchEnabled"
0x9b406  ldc.i4.s 0x15
0x9b408  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b40d  dup
0x9b40e  ldstr    aRequestaccesse// "RequestAccessEmail"
0x9b413  ldc.i4.s 0x16
0x9b415  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b41a  dup
0x9b41b  ldstr    aSavesiteastemp// "SaveSiteAsTemplateEnabled"
0x9b420  ldc.i4.s 0x17
0x9b422  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b427  dup
0x9b428  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x9b42d  ldc.i4.s 0x18
0x9b42f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b434  dup
0x9b435  ldstr    aSitelogodescri// "SiteLogoDescription"
0x9b43a  ldc.i4.s 0x19
0x9b43c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b441  dup
0x9b442  ldstr    aSitelogourl// "SiteLogoUrl"
0x9b447  ldc.i4.s 0x1A
0x9b449  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b44e  dup
0x9b44f  ldstr    aSyndicationena// "SyndicationEnabled"
0x9b454  ldc.i4.s 0x1B
0x9b456  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b45b  dup
0x9b45c  ldstr    aThemedcssfolde// "ThemedCssFolderUrl"
0x9b461  ldc.i4.s 0x1C
0x9b463  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b468  dup
0x9b469  ldstr    aTitle// "Title"
0x9b46e  ldc.i4.s 0x1D
0x9b470  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b475  dup
0x9b476  ldstr    aTreeviewenable// "TreeViewEnabled"
0x9b47b  ldc.i4.s 0x1E
0x9b47d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b482  dup
0x9b483  ldstr    aUiversion// "UIVersion"
0x9b488  ldc.i4.s 0x1F
0x9b48a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b48f  dup
0x9b490  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x9b495  ldc.i4.s 0x20
0x9b497  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b49c  volatile.
0x9b49e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600191e-1
0x9b4a3  volatile.
0x9b4a5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600191e-1
0x9b4aa  ldloc.1
0x9b4ab  ldloca.s 2
0x9b4ad  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x9b4b2  brfalse  loc_9B8A0
0x9b4b7  ldloc.2
0x9b4b8  switch   loc_9B546, loc_9B560, loc_9B57A, loc_9B594, loc_9B5AE, loc_9B5C8, loc_9B5E2, loc_9B5FC, loc_9B616, loc_9B630, loc_9B64A, loc_9B664, loc_9B67E, loc_9B698, loc_9B6B2, loc_9B6CC, loc_9B6E6, loc_9B700, loc_9B71A, loc_9B734, loc_9B74E, loc_9B768, loc_9B782, loc_9B79C, loc_9B7B6, loc_9B7D0, loc_9B7EA, loc_9B804, loc_9B81E, loc_9B838, loc_9B852, loc_9B86C, loc_9B886
0x9b541  br       loc_9B8A0
0x9b546  ldarg.0
0x9b547  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x9b54c  ldarg.s  4
0x9b54e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b553  ldloc.0
0x9b554  ldarg.3
0x9b555  callvirt T0x2B00000A
0x9b55a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AllowAutomaticASPXPageIndexing(bool)
0x9b55f  ret
0x9b560  ldarg.0
0x9b561  ldstr    aAlternatecssur// "AlternateCssUrl"
0x9b566  ldarg.s  4
0x9b568  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b56d  ldloc.0
0x9b56e  ldarg.3
0x9b56f  callvirt T0x2B000008
0x9b574  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AlternateCssUrl(string)
0x9b579  ret
0x9b57a  ldarg.0
0x9b57b  ldstr    aAssociatedmemb// "AssociatedMemberGroup"
0x9b580  ldarg.s  4
0x9b582  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b587  ldloc.0
0x9b588  ldarg.3
0x9b589  callvirt T0x2B0001D1
0x9b58e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AssociatedMemberGroup(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup)
0x9b593  ret
0x9b594  ldarg.0
0x9b595  ldstr    aAssociatedowne// "AssociatedOwnerGroup"
0x9b59a  ldarg.s  4
0x9b59c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b5a1  ldloc.0
0x9b5a2  ldarg.3
0x9b5a3  callvirt T0x2B0001D1
0x9b5a8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AssociatedOwnerGroup(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup)
0x9b5ad  ret
0x9b5ae  ldarg.0
0x9b5af  ldstr    aAssociatedvisi// "AssociatedVisitorGroup"
0x9b5b4  ldarg.s  4
0x9b5b6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b5bb  ldloc.0
0x9b5bc  ldarg.3
0x9b5bd  callvirt T0x2B0001D1
0x9b5c2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AssociatedVisitorGroup(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup)
0x9b5c7  ret
0x9b5c8  ldarg.0
0x9b5c9  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x9b5ce  ldarg.s  4
0x9b5d0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b5d5  ldloc.0
0x9b5d6  ldarg.3
0x9b5d7  callvirt T0x2B00000A
0x9b5dc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_CommentsOnSitePagesDisabled(bool)
0x9b5e1  ret
0x9b5e2  ldarg.0
0x9b5e3  ldstr    aContainsconfid// "ContainsConfidentialInfo"
0x9b5e8  ldarg.s  4
0x9b5ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b5ef  ldloc.0
0x9b5f0  ldarg.3
0x9b5f1  callvirt T0x2B00000A
0x9b5f6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_ContainsConfidentialInfo(bool)
0x9b5fb  ret
0x9b5fc  ldarg.0
0x9b5fd  ldstr    aCustommasterur// "CustomMasterUrl"
0x9b602  ldarg.s  4
0x9b604  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b609  ldloc.0
0x9b60a  ldarg.3
0x9b60b  callvirt T0x2B000008
0x9b610  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_CustomMasterUrl(string)
0x9b615  ret
0x9b616  ldarg.0
0x9b617  ldstr    aDescription// "Description"
0x9b61c  ldarg.s  4
0x9b61e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b623  ldloc.0
0x9b624  ldarg.3
0x9b625  callvirt T0x2B000008
0x9b62a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_Description(string)
0x9b62f  ret
0x9b630  ldarg.0
0x9b631  ldstr    aDesignpackagei// "DesignPackageId"
0x9b636  ldarg.s  4
0x9b638  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b63d  ldloc.0
0x9b63e  ldarg.3
0x9b63f  callvirt T0x2B00002D
0x9b644  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_DesignPackageId(valuetype [mscorlib]System.Guid)
0x9b649  ret
0x9b64a  ldarg.0
0x9b64b  ldstr    aDisableappview// "DisableAppViews"
0x9b650  ldarg.s  4
0x9b652  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b657  ldloc.0
0x9b658  ldarg.3
0x9b659  callvirt T0x2B00000A
0x9b65e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_DisableAppViews(bool)
0x9b663  ret
0x9b664  ldarg.0
0x9b665  ldstr    aDisableflows// "DisableFlows"
0x9b66a  ldarg.s  4
0x9b66c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b671  ldloc.0
0x9b672  ldarg.3
0x9b673  callvirt T0x2B00000A
0x9b678  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_DisableFlows(bool)
0x9b67d  ret
0x9b67e  ldarg.0
0x9b67f  ldstr    aEnableminimald// "EnableMinimalDownload"
0x9b684  ldarg.s  4
0x9b686  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b68b  ldloc.0
0x9b68c  ldarg.3
0x9b68d  callvirt T0x2B00000A
0x9b692  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_EnableMinimalDownload(bool)
0x9b697  ret
0x9b698  ldarg.0
0x9b699  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x9b69e  ldarg.s  4
0x9b6a0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b6a5  ldloc.0
0x9b6a6  ldarg.3
0x9b6a7  callvirt T0x2B00000A
0x9b6ac  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_ExcludeFromOfflineClient(bool)
  ... truncated ...
```
