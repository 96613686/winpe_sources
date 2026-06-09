# Microsoft.SharePoint.ServerStub.SPWebServerStub::SetProperty

- ea: `0x95770`
- end: `0x95dbe`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::SetProperty`
- size: `1614`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x95770`

## string_xrefs

- `0x95805`: `CommentsOnSitePagesDisabled`
- `0x95aa3`: `CommentsOnSitePagesDisabled`
- `0x95960`: `UIVersionConfigurationEnabled`
- `0x95d97`: `UIVersionConfigurationEnabled`
- `0x958c4`: `OverwriteTranslationsOnChange`
- `0x95c47`: `OverwriteTranslationsOnChange`
- `0x958de`: `RequestAccessEmail`
- `0x95c7f`: `RequestAccessEmail`
- `0x958eb`: `SaveSiteAsTemplateEnabled`
- `0x95c9b`: `SaveSiteAsTemplateEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x95770  ldarg.s  4
0x95772  brtrue.s loc_9577F
0x95774  ldstr    aProxycontext// "proxyContext"
0x95779  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9577e  throw
0x9577f  ldarg.1
0x95780  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x95785  stloc.0
0x95786  ldloc.0
0x95787  brtrue.s loc_95794
0x95789  ldstr    aTarget// "target"
0x9578e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x95793  throw
0x95794  ldarg.2
0x95795  brtrue.s loc_957A2
0x95797  ldstr    aPropname// "propName"
0x9579c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x957a1  throw
0x957a2  ldarg.0
0x957a3  ldarg.2
0x957a4  ldarg.s  4
0x957a6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x957ab  starg.s  2
0x957ad  ldarg.2
0x957ae  dup
0x957af  stloc.1
0x957b0  brfalse  loc_95DB2
0x957b5  volatile.
0x957b7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018a5-1
0x957bc  brtrue   loc_95973
0x957c1  ldc.i4.s 0x21
0x957c3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x957c8  dup
0x957c9  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x957ce  ldc.i4.0
0x957cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x957d4  dup
0x957d5  ldstr    aAlternatecssur// "AlternateCssUrl"
0x957da  ldc.i4.1
0x957db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x957e0  dup
0x957e1  ldstr    aAssociatedmemb// "AssociatedMemberGroup"
0x957e6  ldc.i4.2
0x957e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x957ec  dup
0x957ed  ldstr    aAssociatedowne// "AssociatedOwnerGroup"
0x957f2  ldc.i4.3
0x957f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x957f8  dup
0x957f9  ldstr    aAssociatedvisi// "AssociatedVisitorGroup"
0x957fe  ldc.i4.4
0x957ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95804  dup
0x95805  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x9580a  ldc.i4.5
0x9580b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95810  dup
0x95811  ldstr    aContainsconfid// "ContainsConfidentialInfo"
0x95816  ldc.i4.6
0x95817  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9581c  dup
0x9581d  ldstr    aCustommasterur// "CustomMasterUrl"
0x95822  ldc.i4.7
0x95823  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95828  dup
0x95829  ldstr    aDescription// "Description"
0x9582e  ldc.i4.8
0x9582f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95834  dup
0x95835  ldstr    aDesignpackagei// "DesignPackageId"
0x9583a  ldc.i4.s 9
0x9583c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95841  dup
0x95842  ldstr    aDisableappview// "DisableAppViews"
0x95847  ldc.i4.s 0xA
0x95849  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9584e  dup
0x9584f  ldstr    aDisableflows// "DisableFlows"
0x95854  ldc.i4.s 0xB
0x95856  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9585b  dup
0x9585c  ldstr    aEnableminimald// "EnableMinimalDownload"
0x95861  ldc.i4.s 0xC
0x95863  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95868  dup
0x95869  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x9586e  ldc.i4.s 0xD
0x95870  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95875  dup
0x95876  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x9587b  ldc.i4.s 0xE
0x9587d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95882  dup
0x95883  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x95888  ldc.i4.s 0xF
0x9588a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9588f  dup
0x95890  ldstr    aIsmultilingual// "IsMultilingual"
0x95895  ldc.i4.s 0x10
0x95897  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9589c  dup
0x9589d  ldstr    aMasterurl// "MasterUrl"
0x958a2  ldc.i4.s 0x11
0x958a4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x958a9  dup
0x958aa  ldstr    aMemberscanshar// "MembersCanShare"
0x958af  ldc.i4.s 0x12
0x958b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x958b6  dup
0x958b7  ldstr    aNocrawl// "NoCrawl"
0x958bc  ldc.i4.s 0x13
0x958be  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x958c3  dup
0x958c4  ldstr    aOverwritetrans// "OverwriteTranslationsOnChange"
0x958c9  ldc.i4.s 0x14
0x958cb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x958d0  dup
0x958d1  ldstr    aQuicklaunchena// "QuickLaunchEnabled"
0x958d6  ldc.i4.s 0x15
0x958d8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x958dd  dup
0x958de  ldstr    aRequestaccesse// "RequestAccessEmail"
0x958e3  ldc.i4.s 0x16
0x958e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x958ea  dup
0x958eb  ldstr    aSavesiteastemp// "SaveSiteAsTemplateEnabled"
0x958f0  ldc.i4.s 0x17
0x958f2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x958f7  dup
0x958f8  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x958fd  ldc.i4.s 0x18
0x958ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95904  dup
0x95905  ldstr    aSitelogodescri// "SiteLogoDescription"
0x9590a  ldc.i4.s 0x19
0x9590c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95911  dup
0x95912  ldstr    aSitelogourl// "SiteLogoUrl"
0x95917  ldc.i4.s 0x1A
0x95919  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9591e  dup
0x9591f  ldstr    aSyndicationena// "SyndicationEnabled"
0x95924  ldc.i4.s 0x1B
0x95926  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9592b  dup
0x9592c  ldstr    aThemedcssfolde// "ThemedCssFolderUrl"
0x95931  ldc.i4.s 0x1C
0x95933  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95938  dup
0x95939  ldstr    aTitle// "Title"
0x9593e  ldc.i4.s 0x1D
0x95940  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95945  dup
0x95946  ldstr    aTreeviewenable// "TreeViewEnabled"
0x9594b  ldc.i4.s 0x1E
0x9594d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x95952  dup
0x95953  ldstr    aUiversion// "UIVersion"
0x95958  ldc.i4.s 0x1F
0x9595a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9595f  dup
0x95960  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x95965  ldc.i4.s 0x20
0x95967  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9596c  volatile.
0x9596e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018a5-1
0x95973  volatile.
0x95975  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018a5-1
0x9597a  ldloc.1
0x9597b  ldloca.s 2
0x9597d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x95982  brfalse  loc_95DB2
0x95987  ldloc.2
0x95988  switch   loc_95A16, loc_95A32, loc_95A4E, loc_95A6A, loc_95A86, loc_95AA2, loc_95ABE, loc_95ADA, loc_95AF6, loc_95B12, loc_95B2E, loc_95B4A, loc_95B66, loc_95B82, loc_95B9E, loc_95BBA, loc_95BD6, loc_95BF2, loc_95C0E, loc_95C2A, loc_95C46, loc_95C62, loc_95C7E, loc_95C9A, loc_95CB6, loc_95CD2, loc_95CEE, loc_95D0A, loc_95D26, loc_95D42, loc_95D5E, loc_95D7A, loc_95D96
0x95a11  br       loc_95DB2
0x95a16  ldarg.0
0x95a17  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x95a1c  ldarg.s  4
0x95a1e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95a23  ldloc.0
0x95a24  ldarg.3
0x95a25  ldarg.s  4
0x95a27  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95a2c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AllowAutomaticASPXPageIndexing(bool)
0x95a31  ret
0x95a32  ldarg.0
0x95a33  ldstr    aAlternatecssur// "AlternateCssUrl"
0x95a38  ldarg.s  4
0x95a3a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95a3f  ldloc.0
0x95a40  ldarg.3
0x95a41  ldarg.s  4
0x95a43  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95a48  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AlternateCssUrl(string)
0x95a4d  ret
0x95a4e  ldarg.0
0x95a4f  ldstr    aAssociatedmemb// "AssociatedMemberGroup"
0x95a54  ldarg.s  4
0x95a56  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95a5b  ldloc.0
0x95a5c  ldarg.3
0x95a5d  ldarg.s  4
0x95a5f  call     T0x2B0001CE
0x95a64  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AssociatedMemberGroup(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup)
0x95a69  ret
0x95a6a  ldarg.0
0x95a6b  ldstr    aAssociatedowne// "AssociatedOwnerGroup"
0x95a70  ldarg.s  4
0x95a72  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95a77  ldloc.0
0x95a78  ldarg.3
0x95a79  ldarg.s  4
0x95a7b  call     T0x2B0001CE
0x95a80  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AssociatedOwnerGroup(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup)
0x95a85  ret
0x95a86  ldarg.0
0x95a87  ldstr    aAssociatedvisi// "AssociatedVisitorGroup"
0x95a8c  ldarg.s  4
0x95a8e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95a93  ldloc.0
0x95a94  ldarg.3
0x95a95  ldarg.s  4
0x95a97  call     T0x2B0001CE
0x95a9c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AssociatedVisitorGroup(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup)
0x95aa1  ret
0x95aa2  ldarg.0
0x95aa3  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x95aa8  ldarg.s  4
0x95aaa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95aaf  ldloc.0
0x95ab0  ldarg.3
0x95ab1  ldarg.s  4
0x95ab3  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95ab8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_CommentsOnSitePagesDisabled(bool)
0x95abd  ret
0x95abe  ldarg.0
0x95abf  ldstr    aContainsconfid// "ContainsConfidentialInfo"
0x95ac4  ldarg.s  4
0x95ac6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95acb  ldloc.0
0x95acc  ldarg.3
0x95acd  ldarg.s  4
0x95acf  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95ad4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_ContainsConfidentialInfo(bool)
0x95ad9  ret
0x95ada  ldarg.0
0x95adb  ldstr    aCustommasterur// "CustomMasterUrl"
0x95ae0  ldarg.s  4
0x95ae2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95ae7  ldloc.0
0x95ae8  ldarg.3
0x95ae9  ldarg.s  4
0x95aeb  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95af0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_CustomMasterUrl(string)
0x95af5  ret
0x95af6  ldarg.0
0x95af7  ldstr    aDescription// "Description"
0x95afc  ldarg.s  4
0x95afe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b03  ldloc.0
0x95b04  ldarg.3
0x95b05  ldarg.s  4
0x95b07  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b0c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_Description(string)
0x95b11  ret
0x95b12  ldarg.0
0x95b13  ldstr    aDesignpackagei// "DesignPackageId"
0x95b18  ldarg.s  4
0x95b1a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b1f  ldloc.0
0x95b20  ldarg.3
0x95b21  ldarg.s  4
0x95b23  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b28  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_DesignPackageId(valuetype [mscorlib]System.Guid)
0x95b2d  ret
0x95b2e  ldarg.0
0x95b2f  ldstr    aDisableappview// "DisableAppViews"
0x95b34  ldarg.s  4
0x95b36  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b3b  ldloc.0
0x95b3c  ldarg.3
0x95b3d  ldarg.s  4
0x95b3f  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b44  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_DisableAppViews(bool)
0x95b49  ret
0x95b4a  ldarg.0
0x95b4b  ldstr    aDisableflows// "DisableFlows"
0x95b50  ldarg.s  4
0x95b52  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b57  ldloc.0
0x95b58  ldarg.3
0x95b59  ldarg.s  4
0x95b5b  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b60  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_DisableFlows(bool)
0x95b65  ret
0x95b66  ldarg.0
0x95b67  ldstr    aEnableminimald// "EnableMinimalDownload"
0x95b6c  ldarg.s  4
0x95b6e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95b73  ldloc.0
  ... truncated ...
```
