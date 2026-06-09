# Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::SetProperty

- ea: `0xab380`
- end: `0xab7b2`
- name: `Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::SetProperty`
- size: `1074`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xab380`

## string_xrefs

- `0xab42d`: `LinkingUrl`
- `0xab61f`: `LinkingUrl`
- `0xab3fd`: `Extension`
- `0xab5af`: `Extension`
- `0xab4c7`: `UrlPath`
- `0xab76f`: `UrlPath`

## pseudocode

```c

```

## disassembly

```asm
0xab380  ldarg.s  4
0xab382  brtrue.s loc_AB38F
0xab384  ldstr    aProxycontext// "proxyContext"
0xab389  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xab38e  throw
0xab38f  ldarg.1
0xab390  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo
0xab395  stloc.0
0xab396  ldloc.0
0xab397  brtrue.s loc_AB3A4
0xab399  ldstr    aTarget// "target"
0xab39e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xab3a3  throw
0xab3a4  ldarg.2
0xab3a5  brtrue.s loc_AB3B2
0xab3a7  ldstr    aPropname// "propName"
0xab3ac  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xab3b1  throw
0xab3b2  ldarg.0
0xab3b3  ldarg.2
0xab3b4  ldarg.s  4
0xab3b6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab3bb  starg.s  2
0xab3bd  ldarg.2
0xab3be  dup
0xab3bf  stloc.1
0xab3c0  brfalse  loc_AB7A6
0xab3c5  volatile.
0xab3c7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c20-1
0xab3cc  brtrue   loc_AB4E7
0xab3d1  ldc.i4.s 0x15
0xab3d3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xab3d8  dup
0xab3d9  ldstr    aAuthor_0// "Author"
0xab3de  ldc.i4.0
0xab3df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab3e4  dup
0xab3e5  ldstr    aContenttypeid_0// "ContentTypeId"
0xab3ea  ldc.i4.1
0xab3eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab3f0  dup
0xab3f1  ldstr    aEditor// "Editor"
0xab3f6  ldc.i4.2
0xab3f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab3fc  dup
0xab3fd  ldstr    aExtension_0// "Extension"
0xab402  ldc.i4.3
0xab403  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab408  dup
0xab409  ldstr    aFileleafref// "FileLeafRef"
0xab40e  ldc.i4.4
0xab40f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab414  dup
0xab415  ldstr    aFileref// "FileRef"
0xab41a  ldc.i4.5
0xab41b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab420  dup
0xab421  ldstr    aIscontainer// "IsContainer"
0xab426  ldc.i4.6
0xab427  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab42c  dup
0xab42d  ldstr    aLinkingurl// "LinkingUrl"
0xab432  ldc.i4.7
0xab433  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab438  dup
0xab439  ldstr    aListid_0// "ListId"
0xab43e  ldc.i4.8
0xab43f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab444  dup
0xab445  ldstr    aListitemid// "ListItemId"
0xab44a  ldc.i4.s 9
0xab44c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab451  dup
0xab452  ldstr    aModified// "Modified"
0xab457  ldc.i4.s 0xA
0xab459  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab45e  dup
0xab45f  ldstr    aProgid_1// "ProgId"
0xab464  ldc.i4.s 0xB
0xab466  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab46b  dup
0xab46c  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xab471  ldc.i4.s 0xC
0xab473  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab478  dup
0xab479  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xab47e  ldc.i4.s 0xD
0xab480  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab485  dup
0xab486  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xab48b  ldc.i4.s 0xE
0xab48d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab492  dup
0xab493  ldstr    aSiteid_0// "SiteId"
0xab498  ldc.i4.s 0xF
0xab49a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab49f  dup
0xab4a0  ldstr    aSiteurl_0// "SiteUrl"
0xab4a5  ldc.i4.s 0x10
0xab4a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab4ac  dup
0xab4ad  ldstr    aTitle// "Title"
0xab4b2  ldc.i4.s 0x11
0xab4b4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab4b9  dup
0xab4ba  ldstr    aUniqueid_0// "UniqueId"
0xab4bf  ldc.i4.s 0x12
0xab4c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab4c6  dup
0xab4c7  ldstr    aUrlpath// "UrlPath"
0xab4cc  ldc.i4.s 0x13
0xab4ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab4d3  dup
0xab4d4  ldstr    aWebid_0// "WebId"
0xab4d9  ldc.i4.s 0x14
0xab4db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xab4e0  volatile.
0xab4e2  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c20-1
0xab4e7  volatile.
0xab4e9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c20-1
0xab4ee  ldloc.1
0xab4ef  ldloca.s 2
0xab4f1  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xab4f6  brfalse  loc_AB7A6
0xab4fb  ldloc.2
0xab4fc  switch   loc_AB55A, loc_AB576, loc_AB592, loc_AB5AE, loc_AB5CA, loc_AB5E6, loc_AB602, loc_AB61E, loc_AB63A, loc_AB656, loc_AB672, loc_AB68E, loc_AB6AA, loc_AB6C6, loc_AB6E2, loc_AB6FE, loc_AB71A, loc_AB736, loc_AB752, loc_AB76E, loc_AB78A
0xab555  br       loc_AB7A6
0xab55a  ldarg.0
0xab55b  ldstr    aAuthor_0// "Author"
0xab560  ldarg.s  4
0xab562  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab567  ldloc.0
0xab568  ldarg.3
0xab569  ldarg.s  4
0xab56b  call     T0x2B000098
0xab570  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Author(class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal)
0xab575  ret
0xab576  ldarg.0
0xab577  ldstr    aContenttypeid_0// "ContentTypeId"
0xab57c  ldarg.s  4
0xab57e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab583  ldloc.0
0xab584  ldarg.3
0xab585  ldarg.s  4
0xab587  call     T0x2B00022A
0xab58c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ContentTypeId(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId)
0xab591  ret
0xab592  ldarg.0
0xab593  ldstr    aEditor// "Editor"
0xab598  ldarg.s  4
0xab59a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab59f  ldloc.0
0xab5a0  ldarg.3
0xab5a1  ldarg.s  4
0xab5a3  call     T0x2B000098
0xab5a8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Editor(class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal)
0xab5ad  ret
0xab5ae  ldarg.0
0xab5af  ldstr    aExtension_0// "Extension"
0xab5b4  ldarg.s  4
0xab5b6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab5bb  ldloc.0
0xab5bc  ldarg.3
0xab5bd  ldarg.s  4
0xab5bf  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab5c4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Extension(string)
0xab5c9  ret
0xab5ca  ldarg.0
0xab5cb  ldstr    aFileleafref// "FileLeafRef"
0xab5d0  ldarg.s  4
0xab5d2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab5d7  ldloc.0
0xab5d8  ldarg.3
0xab5d9  ldarg.s  4
0xab5db  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab5e0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_FileLeafRef(string)
0xab5e5  ret
0xab5e6  ldarg.0
0xab5e7  ldstr    aFileref// "FileRef"
0xab5ec  ldarg.s  4
0xab5ee  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab5f3  ldloc.0
0xab5f4  ldarg.3
0xab5f5  ldarg.s  4
0xab5f7  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab5fc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_FileRef(string)
0xab601  ret
0xab602  ldarg.0
0xab603  ldstr    aIscontainer// "IsContainer"
0xab608  ldarg.s  4
0xab60a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab60f  ldloc.0
0xab610  ldarg.3
0xab611  ldarg.s  4
0xab613  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab618  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_IsContainer(bool)
0xab61d  ret
0xab61e  ldarg.0
0xab61f  ldstr    aLinkingurl// "LinkingUrl"
0xab624  ldarg.s  4
0xab626  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab62b  ldloc.0
0xab62c  ldarg.3
0xab62d  ldarg.s  4
0xab62f  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab634  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_LinkingUrl(string)
0xab639  ret
0xab63a  ldarg.0
0xab63b  ldstr    aListid_0// "ListId"
0xab640  ldarg.s  4
0xab642  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab647  ldloc.0
0xab648  ldarg.3
0xab649  ldarg.s  4
0xab64b  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab650  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ListId(valuetype [mscorlib]System.Guid)
0xab655  ret
0xab656  ldarg.0
0xab657  ldstr    aListitemid// "ListItemId"
0xab65c  ldarg.s  4
0xab65e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab663  ldloc.0
0xab664  ldarg.3
0xab665  ldarg.s  4
0xab667  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab66c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ListItemId(int32)
0xab671  ret
0xab672  ldarg.0
0xab673  ldstr    aModified// "Modified"
0xab678  ldarg.s  4
0xab67a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab67f  ldloc.0
0xab680  ldarg.3
0xab681  ldarg.s  4
0xab683  call     valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToDateTime(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab688  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Modified(valuetype [mscorlib]System.DateTime)
0xab68d  ret
0xab68e  ldarg.0
0xab68f  ldstr    aProgid_1// "ProgId"
0xab694  ldarg.s  4
0xab696  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab69b  ldloc.0
0xab69c  ldarg.3
0xab69d  ldarg.s  4
0xab69f  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab6a4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ProgId(string)
0xab6a9  ret
0xab6aa  ldarg.0
0xab6ab  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xab6b0  ldarg.s  4
0xab6b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab6b7  ldloc.0
0xab6b8  ldarg.3
0xab6b9  ldarg.s  4
0xab6bb  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab6c0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ServerRedirectedEmbedUrl(string)
0xab6c5  ret
0xab6c6  ldarg.0
0xab6c7  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xab6cc  ldarg.s  4
0xab6ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab6d3  ldloc.0
0xab6d4  ldarg.3
0xab6d5  ldarg.s  4
0xab6d7  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab6dc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ServerRedirectedPreviewUrl(string)
0xab6e1  ret
0xab6e2  ldarg.0
0xab6e3  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xab6e8  ldarg.s  4
0xab6ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab6ef  ldloc.0
0xab6f0  ldarg.3
0xab6f1  ldarg.s  4
0xab6f3  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab6f8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ServerRedirectedUrl(string)
0xab6fd  ret
0xab6fe  ldarg.0
0xab6ff  ldstr    aSiteid_0// "SiteId"
0xab704  ldarg.s  4
0xab706  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab70b  ldloc.0
0xab70c  ldarg.3
0xab70d  ldarg.s  4
0xab70f  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab714  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_SiteId(valuetype [mscorlib]System.Guid)
0xab719  ret
0xab71a  ldarg.0
0xab71b  ldstr    aSiteurl_0// "SiteUrl"
0xab720  ldarg.s  4
0xab722  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab727  ldloc.0
0xab728  ldarg.3
0xab729  ldarg.s  4
0xab72b  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab730  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_SiteUrl(string)
0xab735  ret
0xab736  ldarg.0
0xab737  ldstr    aTitle// "Title"
0xab73c  ldarg.s  4
  ... truncated ...
```
