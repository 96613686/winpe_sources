# Microsoft.SharePoint.ServerStub.SPListServerStub::SetProperty

- ea: `0x36d0`
- end: `0x3eb3`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::SetProperty`
- size: `2019`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x36d0`

## string_xrefs

- `0x3795`: `DocumentTemplateUrl`
- `0x3b0c`: `DocumentTemplateUrl`
- `0x3831`: `ImagePath`
- `0x3c5c`: `ImagePath`
- `0x3901`: `ReadSecurity`
- `0x3e1c`: `ReadSecurity`
- `0x3935`: `WriteSecurity`
- `0x3e8c`: `WriteSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x36d0  ldarg.s  4
0x36d2  brtrue.s loc_36DF
0x36d4  ldstr    aProxycontext// "proxyContext"
0x36d9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x36de  throw
0x36df  ldarg.1
0x36e0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x36e5  stloc.0
0x36e6  ldloc.0
0x36e7  brtrue.s loc_36F4
0x36e9  ldstr    aTarget// "target"
0x36ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x36f3  throw
0x36f4  ldarg.2
0x36f5  brtrue.s loc_3702
0x36f7  ldstr    aPropname// "propName"
0x36fc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3701  throw
0x3702  ldarg.0
0x3703  ldarg.2
0x3704  ldarg.s  4
0x3706  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x370b  starg.s  2
0x370d  ldarg.2
0x370e  dup
0x370f  stloc.1
0x3710  brfalse  loc_3EA7
0x3715  volatile.
0x3717  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000091-1
0x371c  brtrue   loc_3948
0x3721  ldc.i4.s 0x2A
0x3723  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3728  dup
0x3729  ldstr    aAllowdeletion// "AllowDeletion"
0x372e  ldc.i4.0
0x372f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3734  dup
0x3735  ldstr    aContenttypesen// "ContentTypesEnabled"
0x373a  ldc.i4.1
0x373b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3740  dup
0x3741  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x3746  ldc.i4.2
0x3747  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x374c  dup
0x374d  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x3752  ldc.i4.3
0x3753  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3758  dup
0x3759  ldstr    aDefaultdisplay// "DefaultDisplayFormUrl"
0x375e  ldc.i4.4
0x375f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3764  dup
0x3765  ldstr    aDefaulteditfor// "DefaultEditFormUrl"
0x376a  ldc.i4.5
0x376b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3770  dup
0x3771  ldstr    aDefaultnewform// "DefaultNewFormUrl"
0x3776  ldc.i4.6
0x3777  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x377c  dup
0x377d  ldstr    aDescription// "Description"
0x3782  ldc.i4.7
0x3783  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3788  dup
0x3789  ldstr    aDirection// "Direction"
0x378e  ldc.i4.8
0x378f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3794  dup
0x3795  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x379a  ldc.i4.s 9
0x379c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37a1  dup
0x37a2  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x37a7  ldc.i4.s 0xA
0x37a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37ae  dup
0x37af  ldstr    aEnableassignto// "EnableAssignToEmail"
0x37b4  ldc.i4.s 0xB
0x37b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37bb  dup
0x37bc  ldstr    aEnableattachme// "EnableAttachments"
0x37c1  ldc.i4.s 0xC
0x37c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37c8  dup
0x37c9  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x37ce  ldc.i4.s 0xD
0x37d0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37d5  dup
0x37d6  ldstr    aEnableminorver// "EnableMinorVersions"
0x37db  ldc.i4.s 0xE
0x37dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37e2  dup
0x37e3  ldstr    aEnablemoderati// "EnableModeration"
0x37e8  ldc.i4.s 0xF
0x37ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37ef  dup
0x37f0  ldstr    aEnableversioni// "EnableVersioning"
0x37f5  ldc.i4.s 0x10
0x37f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x37fc  dup
0x37fd  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x3802  ldc.i4.s 0x11
0x3804  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3809  dup
0x380a  ldstr    aExemptfrombloc// "ExemptFromBlockDownloadOfNonViewableFil"...
0x380f  ldc.i4.s 0x12
0x3811  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3816  dup
0x3817  ldstr    aForcecheckout// "ForceCheckout"
0x381c  ldc.i4.s 0x13
0x381e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3823  dup
0x3824  ldstr    aHidden// "Hidden"
0x3829  ldc.i4.s 0x14
0x382b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3830  dup
0x3831  ldstr    aImagepath// "ImagePath"
0x3836  ldc.i4.s 0x15
0x3838  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x383d  dup
0x383e  ldstr    aImageurl// "ImageUrl"
0x3843  ldc.i4.s 0x16
0x3845  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x384a  dup
0x384b  ldstr    aIrmenabled// "IrmEnabled"
0x3850  ldc.i4.s 0x17
0x3852  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3857  dup
0x3858  ldstr    aIrmexpire// "IrmExpire"
0x385d  ldc.i4.s 0x18
0x385f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3864  dup
0x3865  ldstr    aIrmreject// "IrmReject"
0x386a  ldc.i4.s 0x19
0x386c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3871  dup
0x3872  ldstr    aIsapplicationl// "IsApplicationList"
0x3877  ldc.i4.s 0x1A
0x3879  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x387e  dup
0x387f  ldstr    aIsenterprisega// "IsEnterpriseGalleryLibrary"
0x3884  ldc.i4.s 0x1B
0x3886  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x388b  dup
0x388c  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x3891  ldc.i4.s 0x1C
0x3893  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3898  dup
0x3899  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x389e  ldc.i4.s 0x1D
0x38a0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x38a5  dup
0x38a6  ldstr    aListexperience// "ListExperienceOptions"
0x38ab  ldc.i4.s 0x1E
0x38ad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x38b2  dup
0x38b3  ldstr    aMajorversionli// "MajorVersionLimit"
0x38b8  ldc.i4.s 0x1F
0x38ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x38bf  dup
0x38c0  ldstr    aMajorwithminor// "MajorWithMinorVersionsLimit"
0x38c5  ldc.i4.s 0x20
0x38c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x38cc  dup
0x38cd  ldstr    aMultipledatali// "MultipleDataList"
0x38d2  ldc.i4.s 0x21
0x38d4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x38d9  dup
0x38da  ldstr    aNocrawl// "NoCrawl"
0x38df  ldc.i4.s 0x22
0x38e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x38e6  dup
0x38e7  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x38ec  ldc.i4.s 0x23
0x38ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x38f3  dup
0x38f4  ldstr    aParserdisabled// "ParserDisabled"
0x38f9  ldc.i4.s 0x24
0x38fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3900  dup
0x3901  ldstr    aReadsecurity// "ReadSecurity"
0x3906  ldc.i4.s 0x25
0x3908  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x390d  dup
0x390e  ldstr    aTitle// "Title"
0x3913  ldc.i4.s 0x26
0x3915  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x391a  dup
0x391b  ldstr    aValidationform// "ValidationFormula"
0x3920  ldc.i4.s 0x27
0x3922  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3927  dup
0x3928  ldstr    aValidationmess// "ValidationMessage"
0x392d  ldc.i4.s 0x28
0x392f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3934  dup
0x3935  ldstr    aWritesecurity// "WriteSecurity"
0x393a  ldc.i4.s 0x29
0x393c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3941  volatile.
0x3943  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000091-1
0x3948  volatile.
0x394a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000091-1
0x394f  ldloc.1
0x3950  ldloca.s 2
0x3952  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x3957  brfalse  loc_3EA7
0x395c  ldloc.2
0x395d  switch   loc_3A0F, loc_3A2B, loc_3A47, loc_3A63, loc_3A7F, loc_3A9B, loc_3AB7, loc_3AD3, loc_3AEF, loc_3B0B, loc_3B27, loc_3B43, loc_3B5F, loc_3B7B, loc_3B97, loc_3BB3, loc_3BCF, loc_3BEB, loc_3C07, loc_3C23, loc_3C3F, loc_3C5B, loc_3C77, loc_3C93, loc_3CAF, loc_3CCB, loc_3CE7, loc_3D03, loc_3D1F, loc_3D3B, loc_3D57, loc_3D73, loc_3D8F, loc_3DAB, loc_3DC7, loc_3DE3, loc_3DFF, loc_3E1B, loc_3E37, loc_3E53, loc_3E6F, loc_3E8B
0x3a0a  br       loc_3EA7
0x3a0f  ldarg.0
0x3a10  ldstr    aAllowdeletion// "AllowDeletion"
0x3a15  ldarg.s  4
0x3a17  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a1c  ldloc.0
0x3a1d  ldarg.3
0x3a1e  ldarg.s  4
0x3a20  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a25  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowDeletion(bool)
0x3a2a  ret
0x3a2b  ldarg.0
0x3a2c  ldstr    aContenttypesen// "ContentTypesEnabled"
0x3a31  ldarg.s  4
0x3a33  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a38  ldloc.0
0x3a39  ldarg.3
0x3a3a  ldarg.s  4
0x3a3c  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a41  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_ContentTypesEnabled(bool)
0x3a46  ret
0x3a47  ldarg.0
0x3a48  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x3a4d  ldarg.s  4
0x3a4f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a54  ldloc.0
0x3a55  ldarg.3
0x3a56  ldarg.s  4
0x3a58  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a5d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_CrawlNonDefaultViews(bool)
0x3a62  ret
0x3a63  ldarg.0
0x3a64  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x3a69  ldarg.s  4
0x3a6b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a70  ldloc.0
0x3a71  ldarg.3
0x3a72  ldarg.s  4
0x3a74  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a79  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultContentApprovalWorkflowId(valuetype [mscorlib]System.Guid)
0x3a7e  ret
0x3a7f  ldarg.0
0x3a80  ldstr    aDefaultdisplay// "DefaultDisplayFormUrl"
0x3a85  ldarg.s  4
0x3a87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a8c  ldloc.0
0x3a8d  ldarg.3
0x3a8e  ldarg.s  4
0x3a90  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3a95  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultDisplayFormUrl(string)
0x3a9a  ret
0x3a9b  ldarg.0
0x3a9c  ldstr    aDefaulteditfor// "DefaultEditFormUrl"
0x3aa1  ldarg.s  4
0x3aa3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3aa8  ldloc.0
0x3aa9  ldarg.3
0x3aaa  ldarg.s  4
0x3aac  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3ab1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultEditFormUrl(string)
0x3ab6  ret
0x3ab7  ldarg.0
0x3ab8  ldstr    aDefaultnewform// "DefaultNewFormUrl"
0x3abd  ldarg.s  4
0x3abf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3ac4  ldloc.0
0x3ac5  ldarg.3
0x3ac6  ldarg.s  4
0x3ac8  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3acd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_DefaultNewFormUrl(string)
0x3ad2  ret
0x3ad3  ldarg.0
0x3ad4  ldstr    aDescription// "Description"
0x3ad9  ldarg.s  4
0x3adb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3ae0  ldloc.0
0x3ae1  ldarg.3
0x3ae2  ldarg.s  4
0x3ae4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3ae9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Description(string)
0x3aee  ret
0x3aef  ldarg.0
0x3af0  ldstr    aDirection// "Direction"
0x3af5  ldarg.s  4
0x3af7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3afc  ldloc.0
0x3afd  ldarg.3
0x3afe  ldarg.s  4
0x3b00  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3b05  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Direction(string)
  ... truncated ...
```
