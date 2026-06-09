# Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::SetProperty_0

- ea: `0xac800`
- end: `0xacc08`
- name: `Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::SetProperty_0`
- size: `1032`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xac800`

## string_xrefs

- `0xac8ad`: `LinkingUrl`
- `0xaca91`: `LinkingUrl`
- `0xac87d`: `Extension`
- `0xaca29`: `Extension`
- `0xac947`: `UrlPath`
- `0xacbc9`: `UrlPath`

## pseudocode

```c

```

## disassembly

```asm
0xac800  ldarg.s  4
0xac802  brtrue.s loc_AC80F
0xac804  ldstr    aProxycontext// "proxyContext"
0xac809  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xac80e  throw
0xac80f  ldarg.1
0xac810  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo
0xac815  stloc.0
0xac816  ldloc.0
0xac817  brtrue.s loc_AC824
0xac819  ldstr    aTarget// "target"
0xac81e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xac823  throw
0xac824  ldarg.2
0xac825  brtrue.s loc_AC832
0xac827  ldstr    aPropname// "propName"
0xac82c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xac831  throw
0xac832  ldarg.0
0xac833  ldarg.2
0xac834  ldarg.s  4
0xac836  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac83b  starg.s  2
0xac83d  ldarg.2
0xac83e  dup
0xac83f  stloc.1
0xac840  brfalse  loc_ACBFC
0xac845  volatile.
0xac847  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c28-1
0xac84c  brtrue   loc_AC967
0xac851  ldc.i4.s 0x15
0xac853  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xac858  dup
0xac859  ldstr    aAuthor_0// "Author"
0xac85e  ldc.i4.0
0xac85f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac864  dup
0xac865  ldstr    aContenttypeid_0// "ContentTypeId"
0xac86a  ldc.i4.1
0xac86b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac870  dup
0xac871  ldstr    aEditor// "Editor"
0xac876  ldc.i4.2
0xac877  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac87c  dup
0xac87d  ldstr    aExtension_0// "Extension"
0xac882  ldc.i4.3
0xac883  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac888  dup
0xac889  ldstr    aFileleafref// "FileLeafRef"
0xac88e  ldc.i4.4
0xac88f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac894  dup
0xac895  ldstr    aFileref// "FileRef"
0xac89a  ldc.i4.5
0xac89b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8a0  dup
0xac8a1  ldstr    aIscontainer// "IsContainer"
0xac8a6  ldc.i4.6
0xac8a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8ac  dup
0xac8ad  ldstr    aLinkingurl// "LinkingUrl"
0xac8b2  ldc.i4.7
0xac8b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8b8  dup
0xac8b9  ldstr    aListid_0// "ListId"
0xac8be  ldc.i4.8
0xac8bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8c4  dup
0xac8c5  ldstr    aListitemid// "ListItemId"
0xac8ca  ldc.i4.s 9
0xac8cc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8d1  dup
0xac8d2  ldstr    aModified// "Modified"
0xac8d7  ldc.i4.s 0xA
0xac8d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8de  dup
0xac8df  ldstr    aProgid_1// "ProgId"
0xac8e4  ldc.i4.s 0xB
0xac8e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8eb  dup
0xac8ec  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xac8f1  ldc.i4.s 0xC
0xac8f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac8f8  dup
0xac8f9  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xac8fe  ldc.i4.s 0xD
0xac900  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac905  dup
0xac906  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xac90b  ldc.i4.s 0xE
0xac90d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac912  dup
0xac913  ldstr    aSiteid_0// "SiteId"
0xac918  ldc.i4.s 0xF
0xac91a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac91f  dup
0xac920  ldstr    aSiteurl_0// "SiteUrl"
0xac925  ldc.i4.s 0x10
0xac927  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac92c  dup
0xac92d  ldstr    aTitle// "Title"
0xac932  ldc.i4.s 0x11
0xac934  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac939  dup
0xac93a  ldstr    aUniqueid_0// "UniqueId"
0xac93f  ldc.i4.s 0x12
0xac941  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac946  dup
0xac947  ldstr    aUrlpath// "UrlPath"
0xac94c  ldc.i4.s 0x13
0xac94e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac953  dup
0xac954  ldstr    aWebid_0// "WebId"
0xac959  ldc.i4.s 0x14
0xac95b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xac960  volatile.
0xac962  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c28-1
0xac967  volatile.
0xac969  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c28-1
0xac96e  ldloc.1
0xac96f  ldloca.s 2
0xac971  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xac976  brfalse  loc_ACBFC
0xac97b  ldloc.2
0xac97c  switch   loc_AC9DA, loc_AC9F4, loc_ACA0E, loc_ACA28, loc_ACA42, loc_ACA5C, loc_ACA76, loc_ACA90, loc_ACAAA, loc_ACAC4, loc_ACADE, loc_ACAF8, loc_ACB12, loc_ACB2C, loc_ACB46, loc_ACB60, loc_ACB7A, loc_ACB94, loc_ACBAE, loc_ACBC8, loc_ACBE2
0xac9d5  br       loc_ACBFC
0xac9da  ldarg.0
0xac9db  ldstr    aAuthor_0// "Author"
0xac9e0  ldarg.s  4
0xac9e2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac9e7  ldloc.0
0xac9e8  ldarg.3
0xac9e9  callvirt T0x2B00009A
0xac9ee  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Author(class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal)
0xac9f3  ret
0xac9f4  ldarg.0
0xac9f5  ldstr    aContenttypeid_0// "ContentTypeId"
0xac9fa  ldarg.s  4
0xac9fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaca01  ldloc.0
0xaca02  ldarg.3
0xaca03  callvirt T0x2B00022F
0xaca08  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ContentTypeId(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId)
0xaca0d  ret
0xaca0e  ldarg.0
0xaca0f  ldstr    aEditor// "Editor"
0xaca14  ldarg.s  4
0xaca16  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaca1b  ldloc.0
0xaca1c  ldarg.3
0xaca1d  callvirt T0x2B00009A
0xaca22  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Editor(class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal)
0xaca27  ret
0xaca28  ldarg.0
0xaca29  ldstr    aExtension_0// "Extension"
0xaca2e  ldarg.s  4
0xaca30  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaca35  ldloc.0
0xaca36  ldarg.3
0xaca37  callvirt T0x2B000008
0xaca3c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Extension(string)
0xaca41  ret
0xaca42  ldarg.0
0xaca43  ldstr    aFileleafref// "FileLeafRef"
0xaca48  ldarg.s  4
0xaca4a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaca4f  ldloc.0
0xaca50  ldarg.3
0xaca51  callvirt T0x2B000008
0xaca56  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_FileLeafRef(string)
0xaca5b  ret
0xaca5c  ldarg.0
0xaca5d  ldstr    aFileref// "FileRef"
0xaca62  ldarg.s  4
0xaca64  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaca69  ldloc.0
0xaca6a  ldarg.3
0xaca6b  callvirt T0x2B000008
0xaca70  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_FileRef(string)
0xaca75  ret
0xaca76  ldarg.0
0xaca77  ldstr    aIscontainer// "IsContainer"
0xaca7c  ldarg.s  4
0xaca7e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaca83  ldloc.0
0xaca84  ldarg.3
0xaca85  callvirt T0x2B00000A
0xaca8a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_IsContainer(bool)
0xaca8f  ret
0xaca90  ldarg.0
0xaca91  ldstr    aLinkingurl// "LinkingUrl"
0xaca96  ldarg.s  4
0xaca98  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaca9d  ldloc.0
0xaca9e  ldarg.3
0xaca9f  callvirt T0x2B000008
0xacaa4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_LinkingUrl(string)
0xacaa9  ret
0xacaaa  ldarg.0
0xacaab  ldstr    aListid_0// "ListId"
0xacab0  ldarg.s  4
0xacab2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacab7  ldloc.0
0xacab8  ldarg.3
0xacab9  callvirt T0x2B00002D
0xacabe  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ListId(valuetype [mscorlib]System.Guid)
0xacac3  ret
0xacac4  ldarg.0
0xacac5  ldstr    aListitemid// "ListItemId"
0xacaca  ldarg.s  4
0xacacc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacad1  ldloc.0
0xacad2  ldarg.3
0xacad3  callvirt T0x2B000009
0xacad8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ListItemId(int32)
0xacadd  ret
0xacade  ldarg.0
0xacadf  ldstr    aModified// "Modified"
0xacae4  ldarg.s  4
0xacae6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacaeb  ldloc.0
0xacaec  ldarg.3
0xacaed  callvirt T0x2B000045
0xacaf2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Modified(valuetype [mscorlib]System.DateTime)
0xacaf7  ret
0xacaf8  ldarg.0
0xacaf9  ldstr    aProgid_1// "ProgId"
0xacafe  ldarg.s  4
0xacb00  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacb05  ldloc.0
0xacb06  ldarg.3
0xacb07  callvirt T0x2B000008
0xacb0c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ProgId(string)
0xacb11  ret
0xacb12  ldarg.0
0xacb13  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xacb18  ldarg.s  4
0xacb1a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacb1f  ldloc.0
0xacb20  ldarg.3
0xacb21  callvirt T0x2B000008
0xacb26  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ServerRedirectedEmbedUrl(string)
0xacb2b  ret
0xacb2c  ldarg.0
0xacb2d  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xacb32  ldarg.s  4
0xacb34  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacb39  ldloc.0
0xacb3a  ldarg.3
0xacb3b  callvirt T0x2B000008
0xacb40  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ServerRedirectedPreviewUrl(string)
0xacb45  ret
0xacb46  ldarg.0
0xacb47  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xacb4c  ldarg.s  4
0xacb4e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacb53  ldloc.0
0xacb54  ldarg.3
0xacb55  callvirt T0x2B000008
0xacb5a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_ServerRedirectedUrl(string)
0xacb5f  ret
0xacb60  ldarg.0
0xacb61  ldstr    aSiteid_0// "SiteId"
0xacb66  ldarg.s  4
0xacb68  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacb6d  ldloc.0
0xacb6e  ldarg.3
0xacb6f  callvirt T0x2B00002D
0xacb74  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_SiteId(valuetype [mscorlib]System.Guid)
0xacb79  ret
0xacb7a  ldarg.0
0xacb7b  ldstr    aSiteurl_0// "SiteUrl"
0xacb80  ldarg.s  4
0xacb82  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacb87  ldloc.0
0xacb88  ldarg.3
0xacb89  callvirt T0x2B000008
0xacb8e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_SiteUrl(string)
0xacb93  ret
0xacb94  ldarg.0
0xacb95  ldstr    aTitle// "Title"
0xacb9a  ldarg.s  4
0xacb9c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacba1  ldloc.0
0xacba2  ldarg.3
0xacba3  callvirt T0x2B000008
0xacba8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_Title(string)
0xacbad  ret
0xacbae  ldarg.0
0xacbaf  ldstr    aUniqueid_0// "UniqueId"
0xacbb4  ldarg.s  4
0xacbb6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xacbbb  ldloc.0
0xacbbc  ldarg.3
0xacbbd  callvirt T0x2B00002D
0xacbc2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::set_UniqueId(valuetype [mscorlib]System.Guid)
0xacbc7  ret
0xacbc8  ldarg.0
0xacbc9  ldstr    aUrlpath// "UrlPath"
  ... truncated ...
```
