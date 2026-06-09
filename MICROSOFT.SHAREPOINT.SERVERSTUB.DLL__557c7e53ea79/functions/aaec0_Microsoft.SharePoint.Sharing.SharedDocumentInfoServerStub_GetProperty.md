# Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::GetProperty

- ea: `0xaaec0`
- end: `0xab379`
- name: `Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::GetProperty`
- size: `1209`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xaaec0`

## string_xrefs

- `0xaaf77`: `LinkingUrl`
- `0xab1c3`: `LinkingUrl`
- `0xaaf47`: `Extension`
- `0xab172`: `Extension`
- `0xab060`: `UrlPath`
- `0xab332`: `UrlPath`
- `0xab06d`: `VideoManifestUrl`
- `0xab345`: `VideoManifestUrl`

## pseudocode

```c

```

## disassembly

```asm
0xaaec0  ldarg.2
0xaaec1  brtrue.s loc_AAECE
0xaaec3  ldstr    aPropname// "propName"
0xaaec8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaaecd  throw
0xaaece  ldarg.3
0xaaecf  brtrue.s loc_AAEDC
0xaaed1  ldstr    aProxycontext// "proxyContext"
0xaaed6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaaedb  throw
0xaaedc  ldarg.1
0xaaedd  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo
0xaaee2  stloc.0
0xaaee3  ldloc.0
0xaaee4  brtrue.s loc_AAEF1
0xaaee6  ldstr    aTarget// "target"
0xaaeeb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaaef0  throw
0xaaef1  ldarg.0
0xaaef2  ldarg.2
0xaaef3  ldarg.3
0xaaef4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaaef9  starg.s  2
0xaaefb  ldarg.2
0xaaefc  dup
0xaaefd  stloc.1
0xaaefe  brfalse  loc_AB36F
0xaaf03  volatile.
0xaaf05  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c1f-1
0xaaf0a  brtrue   loc_AB08D
0xaaf0f  ldc.i4.s 0x1D
0xaaf11  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xaaf16  dup
0xaaf17  ldstr    aAuthor_0// "Author"
0xaaf1c  ldc.i4.0
0xaaf1d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf22  dup
0xaaf23  ldstr    aCallerstack// "CallerStack"
0xaaf28  ldc.i4.1
0xaaf29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf2e  dup
0xaaf2f  ldstr    aContenttypeid_0// "ContentTypeId"
0xaaf34  ldc.i4.2
0xaaf35  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf3a  dup
0xaaf3b  ldstr    aEditor// "Editor"
0xaaf40  ldc.i4.3
0xaaf41  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf46  dup
0xaaf47  ldstr    aExtension_0// "Extension"
0xaaf4c  ldc.i4.4
0xaaf4d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf52  dup
0xaaf53  ldstr    aFileleafref// "FileLeafRef"
0xaaf58  ldc.i4.5
0xaaf59  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf5e  dup
0xaaf5f  ldstr    aFileref// "FileRef"
0xaaf64  ldc.i4.6
0xaaf65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf6a  dup
0xaaf6b  ldstr    aIscontainer// "IsContainer"
0xaaf70  ldc.i4.7
0xaaf71  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf76  dup
0xaaf77  ldstr    aLinkingurl// "LinkingUrl"
0xaaf7c  ldc.i4.8
0xaaf7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf82  dup
0xaaf83  ldstr    aListid_0// "ListId"
0xaaf88  ldc.i4.s 9
0xaaf8a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf8f  dup
0xaaf90  ldstr    aListitemid// "ListItemId"
0xaaf95  ldc.i4.s 0xA
0xaaf97  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaf9c  dup
0xaaf9d  ldstr    aMediabaseurl// "MediaBaseUrl"
0xaafa2  ldc.i4.s 0xB
0xaafa4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaafa9  dup
0xaafaa  ldstr    aModified// "Modified"
0xaafaf  ldc.i4.s 0xC
0xaafb1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaafb6  dup
0xaafb7  ldstr    aOfficebundlege// "OfficeBundleGenerate"
0xaafbc  ldc.i4.s 0xD
0xaafbe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaafc3  dup
0xaafc4  ldstr    aOfficebundlege_0// "OfficeBundleGetFragment"
0xaafc9  ldc.i4.s 0xE
0xaafcb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaafd0  dup
0xaafd1  ldstr    aPdfconversionu// "PdfConversionUrl"
0xaafd6  ldc.i4.s 0xF
0xaafd8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaafdd  dup
0xaafde  ldstr    aProgid_1// "ProgId"
0xaafe3  ldc.i4.s 0x10
0xaafe5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaafea  dup
0xaafeb  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xaaff0  ldc.i4.s 0x11
0xaaff2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaaff7  dup
0xaaff8  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xaaffd  ldc.i4.s 0x12
0xaafff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab004  dup
0xab005  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xab00a  ldc.i4.s 0x13
0xab00c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab011  dup
0xab012  ldstr    aSiteid_0// "SiteId"
0xab017  ldc.i4.s 0x14
0xab019  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab01e  dup
0xab01f  ldstr    aSiteurl_0// "SiteUrl"
0xab024  ldc.i4.s 0x15
0xab026  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab02b  dup
0xab02c  ldstr    aSpresourceurl// "SpResourceUrl"
0xab031  ldc.i4.s 0x16
0xab033  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab038  dup
0xab039  ldstr    aThumbnailurl// "ThumbnailUrl"
0xab03e  ldc.i4.s 0x17
0xab040  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab045  dup
0xab046  ldstr    aTitle// "Title"
0xab04b  ldc.i4.s 0x18
0xab04d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab052  dup
0xab053  ldstr    aUniqueid_0// "UniqueId"
0xab058  ldc.i4.s 0x19
0xab05a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab05f  dup
0xab060  ldstr    aUrlpath// "UrlPath"
0xab065  ldc.i4.s 0x1A
0xab067  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab06c  dup
0xab06d  ldstr    aVideomanifestu// "VideoManifestUrl"
0xab072  ldc.i4.s 0x1B
0xab074  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab079  dup
0xab07a  ldstr    aWebid_0// "WebId"
0xab07f  ldc.i4.s 0x1C
0xab081  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab086  volatile.
0xab088  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c1f-1
0xab08d  volatile.
0xab08f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c1f-1
0xab094  ldloc.1
0xab095  ldloca.s 2
0xab097  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xab09c  brfalse  loc_AB36F
0xab0a1  ldloc.2
0xab0a2  switch   loc_AB120, loc_AB133, loc_AB146, loc_AB15E, loc_AB171, loc_AB184, loc_AB197, loc_AB1AA, loc_AB1C2, loc_AB1D5, loc_AB1ED, loc_AB205, loc_AB218, loc_AB230, loc_AB243, loc_AB256, loc_AB269, loc_AB27C, loc_AB28F, loc_AB2A2, loc_AB2B5, loc_AB2CD, loc_AB2E0, loc_AB2F3, loc_AB306, loc_AB319, loc_AB331, loc_AB344, loc_AB357
0xab11b  br       loc_AB36F
0xab120  ldarg.0
0xab121  ldstr    aAuthor_0// "Author"
0xab126  ldarg.3
0xab127  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab12c  ldloc.0
0xab12d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Author()
0xab132  ret
0xab133  ldarg.0
0xab134  ldstr    aCallerstack// "CallerStack"
0xab139  ldarg.3
0xab13a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab13f  ldloc.0
0xab140  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_CallerStack()
0xab145  ret
0xab146  ldarg.0
0xab147  ldstr    aContenttypeid_0// "ContentTypeId"
0xab14c  ldarg.3
0xab14d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab152  ldloc.0
0xab153  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ContentTypeId()
0xab158  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xab15d  ret
0xab15e  ldarg.0
0xab15f  ldstr    aEditor// "Editor"
0xab164  ldarg.3
0xab165  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab16a  ldloc.0
0xab16b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Editor()
0xab170  ret
0xab171  ldarg.0
0xab172  ldstr    aExtension_0// "Extension"
0xab177  ldarg.3
0xab178  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab17d  ldloc.0
0xab17e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Extension()
0xab183  ret
0xab184  ldarg.0
0xab185  ldstr    aFileleafref// "FileLeafRef"
0xab18a  ldarg.3
0xab18b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab190  ldloc.0
0xab191  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_FileLeafRef()
0xab196  ret
0xab197  ldarg.0
0xab198  ldstr    aFileref// "FileRef"
0xab19d  ldarg.3
0xab19e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab1a3  ldloc.0
0xab1a4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_FileRef()
0xab1a9  ret
0xab1aa  ldarg.0
0xab1ab  ldstr    aIscontainer// "IsContainer"
0xab1b0  ldarg.3
0xab1b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab1b6  ldloc.0
0xab1b7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_IsContainer()
0xab1bc  box      [mscorlib]System.Boolean
0xab1c1  ret
0xab1c2  ldarg.0
0xab1c3  ldstr    aLinkingurl// "LinkingUrl"
0xab1c8  ldarg.3
0xab1c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab1ce  ldloc.0
0xab1cf  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_LinkingUrl()
0xab1d4  ret
0xab1d5  ldarg.0
0xab1d6  ldstr    aListid_0// "ListId"
0xab1db  ldarg.3
0xab1dc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab1e1  ldloc.0
0xab1e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ListId()
0xab1e7  box      [mscorlib]System.Guid
0xab1ec  ret
0xab1ed  ldarg.0
0xab1ee  ldstr    aListitemid// "ListItemId"
0xab1f3  ldarg.3
0xab1f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab1f9  ldloc.0
0xab1fa  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ListItemId()
0xab1ff  box      [mscorlib]System.Int32
0xab204  ret
0xab205  ldarg.0
0xab206  ldstr    aMediabaseurl// "MediaBaseUrl"
0xab20b  ldarg.3
0xab20c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab211  ldloc.0
0xab212  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_MediaBaseUrl()
0xab217  ret
0xab218  ldarg.0
0xab219  ldstr    aModified// "Modified"
0xab21e  ldarg.3
0xab21f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab224  ldloc.0
0xab225  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Modified()
0xab22a  box      [mscorlib]System.DateTime
0xab22f  ret
0xab230  ldarg.0
0xab231  ldstr    aOfficebundlege// "OfficeBundleGenerate"
0xab236  ldarg.3
0xab237  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab23c  ldloc.0
0xab23d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_OfficeBundleGenerate()
0xab242  ret
0xab243  ldarg.0
0xab244  ldstr    aOfficebundlege_0// "OfficeBundleGetFragment"
0xab249  ldarg.3
0xab24a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab24f  ldloc.0
0xab250  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_OfficeBundleGetFragment()
0xab255  ret
0xab256  ldarg.0
0xab257  ldstr    aPdfconversionu// "PdfConversionUrl"
0xab25c  ldarg.3
0xab25d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab262  ldloc.0
0xab263  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_PdfConversionUrl()
0xab268  ret
0xab269  ldarg.0
0xab26a  ldstr    aProgid_1// "ProgId"
0xab26f  ldarg.3
0xab270  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab275  ldloc.0
0xab276  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ProgId()
0xab27b  ret
0xab27c  ldarg.0
0xab27d  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xab282  ldarg.3
0xab283  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab288  ldloc.0
0xab289  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ServerRedirectedEmbedUrl()
0xab28e  ret
0xab28f  ldarg.0
0xab290  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xab295  ldarg.3
0xab296  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab29b  ldloc.0
0xab29c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ServerRedirectedPreviewUrl()
0xab2a1  ret
0xab2a2  ldarg.0
0xab2a3  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xab2a8  ldarg.3
  ... truncated ...
```
