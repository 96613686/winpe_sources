# Microsoft.SharePoint.ServerStub.SPListServerStub::SetProperty_0

- ea: `0x7fc0`
- end: `0x874f`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::SetProperty_0`
- size: `1935`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7fc0`

## string_xrefs

- `0x8085`: `DocumentTemplateUrl`
- `0x83ea`: `DocumentTemplateUrl`
- `0x8121`: `ImagePath`
- `0x8522`: `ImagePath`
- `0x81f1`: `ReadSecurity`
- `0x86c2`: `ReadSecurity`
- `0x8225`: `WriteSecurity`
- `0x872a`: `WriteSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x7fc0  ldarg.s  4
0x7fc2  brtrue.s loc_7FCF
0x7fc4  ldstr    aProxycontext// "proxyContext"
0x7fc9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7fce  throw
0x7fcf  ldarg.1
0x7fd0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x7fd5  stloc.0
0x7fd6  ldloc.0
0x7fd7  brtrue.s loc_7FE4
0x7fd9  ldstr    aTarget// "target"
0x7fde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7fe3  throw
0x7fe4  ldarg.2
0x7fe5  brtrue.s loc_7FF2
0x7fe7  ldstr    aPropname// "propName"
0x7fec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7ff1  throw
0x7ff2  ldarg.0
0x7ff3  ldarg.2
0x7ff4  ldarg.s  4
0x7ff6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7ffb  starg.s  2
0x7ffd  ldarg.2
0x7ffe  dup
0x7fff  stloc.1
0x8000  brfalse  loc_8743
0x8005  volatile.
0x8007  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60000d7-1
0x800c  brtrue   loc_8238
0x8011  ldc.i4.s 0x2A
0x8013  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8018  dup
0x8019  ldstr    aAllowdeletion// "AllowDeletion"
0x801e  ldc.i4.0
0x801f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8024  dup
0x8025  ldstr    aContenttypesen// "ContentTypesEnabled"
0x802a  ldc.i4.1
0x802b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8030  dup
0x8031  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x8036  ldc.i4.2
0x8037  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x803c  dup
0x803d  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x8042  ldc.i4.3
0x8043  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8048  dup
0x8049  ldstr    aDefaultdisplay// "DefaultDisplayFormUrl"
0x804e  ldc.i4.4
0x804f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8054  dup
0x8055  ldstr    aDefaulteditfor// "DefaultEditFormUrl"
0x805a  ldc.i4.5
0x805b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8060  dup
0x8061  ldstr    aDefaultnewform// "DefaultNewFormUrl"
0x8066  ldc.i4.6
0x8067  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x806c  dup
0x806d  ldstr    aDescription// "Description"
0x8072  ldc.i4.7
0x8073  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8078  dup
0x8079  ldstr    aDirection// "Direction"
0x807e  ldc.i4.8
0x807f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8084  dup
0x8085  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x808a  ldc.i4.s 9
0x808c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8091  dup
0x8092  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x8097  ldc.i4.s 0xA
0x8099  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x809e  dup
0x809f  ldstr    aEnableassignto// "EnableAssignToEmail"
0x80a4  ldc.i4.s 0xB
0x80a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80ab  dup
0x80ac  ldstr    aEnableattachme// "EnableAttachments"
0x80b1  ldc.i4.s 0xC
0x80b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80b8  dup
0x80b9  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x80be  ldc.i4.s 0xD
0x80c0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80c5  dup
0x80c6  ldstr    aEnableminorver// "EnableMinorVersions"
0x80cb  ldc.i4.s 0xE
0x80cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80d2  dup
0x80d3  ldstr    aEnablemoderati// "EnableModeration"
0x80d8  ldc.i4.s 0xF
0x80da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80df  dup
0x80e0  ldstr    aEnableversioni// "EnableVersioning"
0x80e5  ldc.i4.s 0x10
0x80e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80ec  dup
0x80ed  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x80f2  ldc.i4.s 0x11
0x80f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80f9  dup
0x80fa  ldstr    aExemptfrombloc// "ExemptFromBlockDownloadOfNonViewableFil"...
0x80ff  ldc.i4.s 0x12
0x8101  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8106  dup
0x8107  ldstr    aForcecheckout// "ForceCheckout"
0x810c  ldc.i4.s 0x13
0x810e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8113  dup
0x8114  ldstr    aHidden// "Hidden"
0x8119  ldc.i4.s 0x14
0x811b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8120  dup
0x8121  ldstr    aImagepath// "ImagePath"
0x8126  ldc.i4.s 0x15
0x8128  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x812d  dup
0x812e  ldstr    aImageurl// "ImageUrl"
0x8133  ldc.i4.s 0x16
0x8135  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x813a  dup
0x813b  ldstr    aIrmenabled// "IrmEnabled"
0x8140  ldc.i4.s 0x17
0x8142  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8147  dup
0x8148  ldstr    aIrmexpire// "IrmExpire"
0x814d  ldc.i4.s 0x18
0x814f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8154  dup
0x8155  ldstr    aIrmreject// "IrmReject"
0x815a  ldc.i4.s 0x19
0x815c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8161  dup
0x8162  ldstr    aIsapplicationl// "IsApplicationList"
0x8167  ldc.i4.s 0x1A
0x8169  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x816e  dup
0x816f  ldstr    aIsenterprisega// "IsEnterpriseGalleryLibrary"
0x8174  ldc.i4.s 0x1B
0x8176  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x817b  dup
0x817c  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x8181  ldc.i4.s 0x1C
0x8183  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8188  dup
0x8189  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x818e  ldc.i4.s 0x1D
0x8190  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8195  dup
0x8196  ldstr    aListexperience// "ListExperienceOptions"
0x819b  ldc.i4.s 0x1E
0x819d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81a2  dup
0x81a3  ldstr    aMajorversionli// "MajorVersionLimit"
0x81a8  ldc.i4.s 0x1F
0x81aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81af  dup
0x81b0  ldstr    aMajorwithminor// "MajorWithMinorVersionsLimit"
0x81b5  ldc.i4.s 0x20
0x81b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81bc  dup
0x81bd  ldstr    aMultipledatali// "MultipleDataList"
0x81c2  ldc.i4.s 0x21
0x81c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81c9  dup
0x81ca  ldstr    aNocrawl// "NoCrawl"
0x81cf  ldc.i4.s 0x22
0x81d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81d6  dup
0x81d7  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x81dc  ldc.i4.s 0x23
0x81de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81e3  dup
0x81e4  ldstr    aParserdisabled// "ParserDisabled"
0x81e9  ldc.i4.s 0x24
0x81eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81f0  dup
0x81f1  ldstr    aReadsecurity// "ReadSecurity"
0x81f6  ldc.i4.s 0x25
0x81f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81fd  dup
0x81fe  ldstr    aTitle// "Title"
0x8203  ldc.i4.s 0x26
0x8205  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x820a  dup
0x820b  ldstr    aValidationform// "ValidationFormula"
0x8210  ldc.i4.s 0x27
0x8212  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8217  dup
0x8218  ldstr    aValidationmess// "ValidationMessage"
0x821d  ldc.i4.s 0x28
0x821f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8224  dup
0x8225  ldstr    aWritesecurity// "WriteSecurity"
0x822a  ldc.i4.s 0x29
0x822c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8231  volatile.
0x8233  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60000d7-1
0x8238  volatile.
0x823a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60000d7-1
0x823f  ldloc.1
0x8240  ldloca.s 2
0x8242  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8247  brfalse  loc_8743
0x824c  ldloc.2
0x824d  switch   loc_82FF, loc_8319, loc_8333, loc_834D, loc_8367, loc_8381, loc_839B, loc_83B5, loc_83CF, loc_83E9, loc_8403, loc_841D, loc_8437, loc_8451, loc_846B, loc_8485, loc_849F, loc_84B9, loc_84D3, loc_84ED, loc_8507, loc_8521, loc_853B, loc_8555, loc_856F, loc_8589, loc_85A3, loc_85BD, loc_85D7, loc_85F1, loc_860B, loc_8625, loc_863F, loc_8659, loc_8673, loc_868D, loc_86A7, loc_86C1, loc_86DB, loc_86F5, loc_870F, loc_8729
0x82fa  br       loc_8743
0x82ff  ldarg.0
0x8300  ldstr    aAllowdeletion// "AllowDeletion"
0x8305  ldarg.s  4
0x8307  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x830c  ldloc.0
0x830d  ldarg.3
0x830e  callvirt T0x2B00000A
0x8313  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowDeletion(bool)
0x8318  ret
0x8319  ldarg.0
0x831a  ldstr    aContenttypesen// "ContentTypesEnabled"
0x831f  ldarg.s  4
0x8321  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8326  ldloc.0
0x8327  ldarg.3
0x8328  callvirt T0x2B00000A
0x832d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_ContentTypesEnabled(bool)
0x8332  ret
0x8333  ldarg.0
0x8334  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x8339  ldarg.s  4
0x833b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8340  ldloc.0
0x8341  ldarg.3
0x8342  callvirt T0x2B00000A
0x8347  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_CrawlNonDefaultViews(bool)
0x834c  ret
0x834d  ldarg.0
0x834e  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x8353  ldarg.s  4
0x8355  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x835a  ldloc.0
0x835b  ldarg.3
0x835c  callvirt T0x2B00002D
0x8361  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultContentApprovalWorkflowId(valuetype [mscorlib]System.Guid)
0x8366  ret
0x8367  ldarg.0
0x8368  ldstr    aDefaultdisplay// "DefaultDisplayFormUrl"
0x836d  ldarg.s  4
0x836f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8374  ldloc.0
0x8375  ldarg.3
0x8376  callvirt T0x2B000008
0x837b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultDisplayFormUrl(string)
0x8380  ret
0x8381  ldarg.0
0x8382  ldstr    aDefaulteditfor// "DefaultEditFormUrl"
0x8387  ldarg.s  4
0x8389  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x838e  ldloc.0
0x838f  ldarg.3
0x8390  callvirt T0x2B000008
0x8395  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultEditFormUrl(string)
0x839a  ret
0x839b  ldarg.0
0x839c  ldstr    aDefaultnewform// "DefaultNewFormUrl"
0x83a1  ldarg.s  4
0x83a3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83a8  ldloc.0
0x83a9  ldarg.3
0x83aa  callvirt T0x2B000008
0x83af  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultNewFormUrl(string)
0x83b4  ret
0x83b5  ldarg.0
0x83b6  ldstr    aDescription// "Description"
0x83bb  ldarg.s  4
0x83bd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83c2  ldloc.0
0x83c3  ldarg.3
0x83c4  callvirt T0x2B000008
0x83c9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Description(string)
0x83ce  ret
0x83cf  ldarg.0
0x83d0  ldstr    aDirection// "Direction"
0x83d5  ldarg.s  4
0x83d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83dc  ldloc.0
0x83dd  ldarg.3
0x83de  callvirt T0x2B000008
0x83e3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Direction(string)
0x83e8  ret
0x83e9  ldarg.0
0x83ea  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x83ef  ldarg.s  4
0x83f1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83f6  ldloc.0
0x83f7  ldarg.3
0x83f8  callvirt T0x2B000008
0x83fd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DocumentTemplateUrl_Client(string)
  ... truncated ...
```
