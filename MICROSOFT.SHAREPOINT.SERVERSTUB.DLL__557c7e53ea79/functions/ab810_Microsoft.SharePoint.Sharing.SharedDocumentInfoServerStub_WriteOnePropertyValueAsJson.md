# Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::WriteOnePropertyValueAsJson

- ea: `0xab810`
- end: `0xac2bb`
- name: `Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::WriteOnePropertyValueAsJson`
- size: `2731`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xab810`

## string_xrefs

- `0xab8a8`: `LinkingUrl`
- `0xabcca`: `LinkingUrl`
- `0xab878`: `Extension`
- `0xabba2`: `Extension`
- `0xab991`: `UrlPath`
- `0xac1fe`: `UrlPath`
- `0xab99e`: `VideoManifestUrl`
- `0xac248`: `VideoManifestUrl`

## pseudocode

```c

```

## disassembly

```asm
0xab810  ldc.i4.0
0xab811  stloc.0
0xab812  ldarg.2
0xab813  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo
0xab818  stloc.1
0xab819  ldloc.1
0xab81a  brtrue.s loc_AB827
0xab81c  ldstr    aTarget// "target"
0xab821  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xab826  throw
0xab827  ldarg.3
0xab828  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xab82d  dup
0xab82e  stloc.2
0xab82f  brfalse  loc_AC2AD
0xab834  volatile.
0xab836  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c23-1
0xab83b  brtrue   loc_AB9BE
0xab840  ldc.i4.s 0x1D
0xab842  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xab847  dup
0xab848  ldstr    aAuthor_0// "Author"
0xab84d  ldc.i4.0
0xab84e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab853  dup
0xab854  ldstr    aCallerstack// "CallerStack"
0xab859  ldc.i4.1
0xab85a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab85f  dup
0xab860  ldstr    aContenttypeid_0// "ContentTypeId"
0xab865  ldc.i4.2
0xab866  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab86b  dup
0xab86c  ldstr    aEditor// "Editor"
0xab871  ldc.i4.3
0xab872  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab877  dup
0xab878  ldstr    aExtension_0// "Extension"
0xab87d  ldc.i4.4
0xab87e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab883  dup
0xab884  ldstr    aFileleafref// "FileLeafRef"
0xab889  ldc.i4.5
0xab88a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab88f  dup
0xab890  ldstr    aFileref// "FileRef"
0xab895  ldc.i4.6
0xab896  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab89b  dup
0xab89c  ldstr    aIscontainer// "IsContainer"
0xab8a1  ldc.i4.7
0xab8a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab8a7  dup
0xab8a8  ldstr    aLinkingurl// "LinkingUrl"
0xab8ad  ldc.i4.8
0xab8ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab8b3  dup
0xab8b4  ldstr    aListid_0// "ListId"
0xab8b9  ldc.i4.s 9
0xab8bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab8c0  dup
0xab8c1  ldstr    aListitemid// "ListItemId"
0xab8c6  ldc.i4.s 0xA
0xab8c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab8cd  dup
0xab8ce  ldstr    aMediabaseurl// "MediaBaseUrl"
0xab8d3  ldc.i4.s 0xB
0xab8d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab8da  dup
0xab8db  ldstr    aModified// "Modified"
0xab8e0  ldc.i4.s 0xC
0xab8e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab8e7  dup
0xab8e8  ldstr    aOfficebundlege// "OfficeBundleGenerate"
0xab8ed  ldc.i4.s 0xD
0xab8ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab8f4  dup
0xab8f5  ldstr    aOfficebundlege_0// "OfficeBundleGetFragment"
0xab8fa  ldc.i4.s 0xE
0xab8fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab901  dup
0xab902  ldstr    aPdfconversionu// "PdfConversionUrl"
0xab907  ldc.i4.s 0xF
0xab909  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab90e  dup
0xab90f  ldstr    aProgid_1// "ProgId"
0xab914  ldc.i4.s 0x10
0xab916  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab91b  dup
0xab91c  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xab921  ldc.i4.s 0x11
0xab923  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab928  dup
0xab929  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xab92e  ldc.i4.s 0x12
0xab930  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab935  dup
0xab936  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xab93b  ldc.i4.s 0x13
0xab93d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab942  dup
0xab943  ldstr    aSiteid_0// "SiteId"
0xab948  ldc.i4.s 0x14
0xab94a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab94f  dup
0xab950  ldstr    aSiteurl_0// "SiteUrl"
0xab955  ldc.i4.s 0x15
0xab957  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab95c  dup
0xab95d  ldstr    aSpresourceurl// "SpResourceUrl"
0xab962  ldc.i4.s 0x16
0xab964  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab969  dup
0xab96a  ldstr    aThumbnailurl// "ThumbnailUrl"
0xab96f  ldc.i4.s 0x17
0xab971  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab976  dup
0xab977  ldstr    aTitle// "Title"
0xab97c  ldc.i4.s 0x18
0xab97e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab983  dup
0xab984  ldstr    aUniqueid_0// "UniqueId"
0xab989  ldc.i4.s 0x19
0xab98b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab990  dup
0xab991  ldstr    aUrlpath// "UrlPath"
0xab996  ldc.i4.s 0x1A
0xab998  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab99d  dup
0xab99e  ldstr    aVideomanifestu// "VideoManifestUrl"
0xab9a3  ldc.i4.s 0x1B
0xab9a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab9aa  dup
0xab9ab  ldstr    aWebid_0// "WebId"
0xab9b0  ldc.i4.s 0x1C
0xab9b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab9b7  volatile.
0xab9b9  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c23-1
0xab9be  volatile.
0xab9c0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c23-1
0xab9c5  ldloc.2
0xab9c6  ldloca.s 3
0xab9c8  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xab9cd  brfalse  loc_AC2AD
0xab9d2  ldloc.3
0xab9d3  switch   loc_ABA51, loc_ABA9B, loc_ABAE5, loc_ABB2F, loc_ABB79, loc_ABBC3, loc_ABC0D, loc_ABC57, loc_ABCA1, loc_ABCEB, loc_ABD35, loc_ABD7F, loc_ABDC9, loc_ABE13, loc_ABE5D, loc_ABEA7, loc_ABEF1, loc_ABF3B, loc_ABF85, loc_ABFCF, loc_AC019, loc_AC063, loc_AC0AD, loc_AC0F7, loc_AC141, loc_AC18B, loc_AC1D5, loc_AC21F, loc_AC266
0xaba4c  br       loc_AC2AD
0xaba51  ldarg.3
0xaba52  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaba57  stloc.s  4
0xaba59  ldloca.s 4
0xaba5b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaba60  brfalse.s loc_ABA79
0xaba62  ldarg.3
0xaba63  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaba68  stloc.s  5
0xaba6a  ldloca.s 5
0xaba6c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaba71  brtrue.s loc_ABA79
0xaba73  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaba78  throw
0xaba79  ldarg.0
0xaba7a  ldstr    aAuthor_0// "Author"
0xaba7f  ldarg.s  4
0xaba81  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaba86  ldc.i4.1
0xaba87  stloc.0
0xaba88  ldarg.1
0xaba89  ldloc.1
0xaba8a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Author()
0xaba8f  ldarg.s  4
0xaba91  call     T0x2B000003
0xaba96  br       loc_AC2B9
0xaba9b  ldarg.3
0xaba9c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabaa1  stloc.s  6
0xabaa3  ldloca.s 6
0xabaa5  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xabaaa  brfalse.s loc_ABAC3
0xabaac  ldarg.3
0xabaad  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabab2  stloc.s  7
0xabab4  ldloca.s 7
0xabab6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xababb  brtrue.s loc_ABAC3
0xababd  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xabac2  throw
0xabac3  ldarg.0
0xabac4  ldstr    aCallerstack// "CallerStack"
0xabac9  ldarg.s  4
0xabacb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabad0  ldc.i4.1
0xabad1  stloc.0
0xabad2  ldarg.1
0xabad3  ldloc.1
0xabad4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_CallerStack()
0xabad9  ldarg.s  4
0xabadb  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabae0  br       loc_AC2B9
0xabae5  ldarg.3
0xabae6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabaeb  stloc.s  8
0xabaed  ldloca.s 8
0xabaef  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xabaf4  brfalse.s loc_ABB0D
0xabaf6  ldarg.3
0xabaf7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabafc  stloc.s  9
0xabafe  ldloca.s 9
0xabb00  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xabb05  brtrue.s loc_ABB0D
0xabb07  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xabb0c  throw
0xabb0d  ldarg.0
0xabb0e  ldstr    aContenttypeid_0// "ContentTypeId"
0xabb13  ldarg.s  4
0xabb15  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabb1a  ldc.i4.1
0xabb1b  stloc.0
0xabb1c  ldarg.1
0xabb1d  ldloc.1
0xabb1e  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ContentTypeId()
0xabb23  ldarg.s  4
0xabb25  call     T0x2B000156
0xabb2a  br       loc_AC2B9
0xabb2f  ldarg.3
0xabb30  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabb35  stloc.s  0xA
0xabb37  ldloca.s 0xA
0xabb39  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xabb3e  brfalse.s loc_ABB57
0xabb40  ldarg.3
0xabb41  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabb46  stloc.s  0xB
0xabb48  ldloca.s 0xB
0xabb4a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xabb4f  brtrue.s loc_ABB57
0xabb51  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xabb56  throw
0xabb57  ldarg.0
0xabb58  ldstr    aEditor// "Editor"
0xabb5d  ldarg.s  4
0xabb5f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabb64  ldc.i4.1
0xabb65  stloc.0
0xabb66  ldarg.1
0xabb67  ldloc.1
0xabb68  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Editor()
0xabb6d  ldarg.s  4
0xabb6f  call     T0x2B000003
0xabb74  br       loc_AC2B9
0xabb79  ldarg.3
0xabb7a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabb7f  stloc.s  0xC
0xabb81  ldloca.s 0xC
0xabb83  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xabb88  brfalse.s loc_ABBA1
0xabb8a  ldarg.3
0xabb8b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabb90  stloc.s  0xD
0xabb92  ldloca.s 0xD
0xabb94  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xabb99  brtrue.s loc_ABBA1
0xabb9b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xabba0  throw
0xabba1  ldarg.0
0xabba2  ldstr    aExtension_0// "Extension"
0xabba7  ldarg.s  4
0xabba9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabbae  ldc.i4.1
0xabbaf  stloc.0
0xabbb0  ldarg.1
0xabbb1  ldloc.1
0xabbb2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Extension()
0xabbb7  ldarg.s  4
0xabbb9  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabbbe  br       loc_AC2B9
0xabbc3  ldarg.3
0xabbc4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabbc9  stloc.s  0xE
0xabbcb  ldloca.s 0xE
0xabbcd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xabbd2  brfalse.s loc_ABBEB
0xabbd4  ldarg.3
0xabbd5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xabbda  stloc.s  0xF
0xabbdc  ldloca.s 0xF
0xabbde  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xabbe3  brtrue.s loc_ABBEB
0xabbe5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xabbea  throw
0xabbeb  ldarg.0
0xabbec  ldstr    aFileleafref// "FileLeafRef"
0xabbf1  ldarg.s  4
0xabbf3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabbf8  ldc.i4.1
0xabbf9  stloc.0
0xabbfa  ldarg.1
0xabbfb  ldloc.1
0xabbfc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_FileLeafRef()
  ... truncated ...
```
