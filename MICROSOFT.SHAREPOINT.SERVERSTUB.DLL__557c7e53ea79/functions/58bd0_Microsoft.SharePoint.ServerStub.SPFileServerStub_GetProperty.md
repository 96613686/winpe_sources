# Microsoft.SharePoint.ServerStub.SPFileServerStub::GetProperty

- ea: `0x58bd0`
- end: `0x591f5`
- name: `Microsoft.SharePoint.ServerStub.SPFileServerStub::GetProperty`
- size: `1573`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x58bd0`

## string_xrefs

- `0x58d70`: `ServerRelativePath`
- `0x590ea`: `ServerRelativePath`
- `0x58c4b`: `CheckInComment`
- `0x58f03`: `CheckInComment`
- `0x58cee`: `LinkingUri`
- `0x5901d`: `LinkingUri`
- `0x58cfb`: `LinkingUrl`
- `0x59030`: `LinkingUrl`
- `0x58d97`: `TimeCreated`
- `0x59128`: `TimeCreated`

## pseudocode

```c

```

## disassembly

```asm
0x58bd0  ldarg.2
0x58bd1  brtrue.s loc_58BDE
0x58bd3  ldstr    aPropname// "propName"
0x58bd8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x58bdd  throw
0x58bde  ldarg.3
0x58bdf  brtrue.s loc_58BEC
0x58be1  ldstr    aProxycontext// "proxyContext"
0x58be6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x58beb  throw
0x58bec  ldarg.1
0x58bed  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x58bf2  stloc.0
0x58bf3  ldloc.0
0x58bf4  brtrue.s loc_58C01
0x58bf6  ldstr    aTarget// "target"
0x58bfb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x58c00  throw
0x58c01  ldarg.0
0x58c02  ldarg.2
0x58c03  ldarg.3
0x58c04  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58c09  starg.s  2
0x58c0b  ldarg.2
0x58c0c  dup
0x58c0d  stloc.1
0x58c0e  brfalse  loc_591EB
0x58c13  volatile.
0x58c15  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ff5-1
0x58c1a  brtrue   loc_58E12
0x58c1f  ldc.i4.s 0x26
0x58c21  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x58c26  dup
0x58c27  ldstr    aActivitycapabi// "ActivityCapabilities"
0x58c2c  ldc.i4.0
0x58c2d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c32  dup
0x58c33  ldstr    aAuthor_0// "Author"
0x58c38  ldc.i4.1
0x58c39  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c3e  dup
0x58c3f  ldstr    aCheckedoutbyus// "CheckedOutByUser"
0x58c44  ldc.i4.2
0x58c45  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c4a  dup
0x58c4b  ldstr    aCheckincomment_0// "CheckInComment"
0x58c50  ldc.i4.3
0x58c51  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c56  dup
0x58c57  ldstr    aCheckouttype// "CheckOutType"
0x58c5c  ldc.i4.4
0x58c5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c62  dup
0x58c63  ldstr    aClientactiviti_1// "ClientActivities"
0x58c68  ldc.i4.5
0x58c69  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c6e  dup
0x58c6f  ldstr    aContenttag// "ContentTag"
0x58c74  ldc.i4.6
0x58c75  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c7a  dup
0x58c7b  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x58c80  ldc.i4.7
0x58c81  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c86  dup
0x58c87  ldstr    aListid_0// "ListId"
0x58c8c  ldc.i4.8
0x58c8d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c92  dup
0x58c93  ldstr    aEffectiveinfor// "EffectiveInformationRightsManagementSet"...
0x58c98  ldc.i4.s 9
0x58c9a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58c9f  dup
0x58ca0  ldstr    aEtag_0// "ETag"
0x58ca5  ldc.i4.s 0xA
0x58ca7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58cac  dup
0x58cad  ldstr    aExists// "Exists"
0x58cb2  ldc.i4.s 0xB
0x58cb4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58cb9  dup
0x58cba  ldstr    aInformationrig// "InformationRightsManagementSettings"
0x58cbf  ldc.i4.s 0xC
0x58cc1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58cc6  dup
0x58cc7  ldstr    aIrmenabled// "IrmEnabled"
0x58ccc  ldc.i4.s 0xD
0x58cce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58cd3  dup
0x58cd4  ldstr    aLength// "Length"
0x58cd9  ldc.i4.s 0xE
0x58cdb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58ce0  dup
0x58ce1  ldstr    aLevel// "Level"
0x58ce6  ldc.i4.s 0xF
0x58ce8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58ced  dup
0x58cee  ldstr    aLinkinguri// "LinkingUri"
0x58cf3  ldc.i4.s 0x10
0x58cf5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58cfa  dup
0x58cfb  ldstr    aLinkingurl// "LinkingUrl"
0x58d00  ldc.i4.s 0x11
0x58d02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d07  dup
0x58d08  ldstr    aListitemallfie// "ListItemAllFields"
0x58d0d  ldc.i4.s 0x12
0x58d0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d14  dup
0x58d15  ldstr    aLockedbyuser// "LockedByUser"
0x58d1a  ldc.i4.s 0x13
0x58d1c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d21  dup
0x58d22  ldstr    aMajorversion// "MajorVersion"
0x58d27  ldc.i4.s 0x14
0x58d29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d2e  dup
0x58d2f  ldstr    aMinorversion// "MinorVersion"
0x58d34  ldc.i4.s 0x15
0x58d36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d3b  dup
0x58d3c  ldstr    aModifiedby// "ModifiedBy"
0x58d41  ldc.i4.s 0x16
0x58d43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d48  dup
0x58d49  ldstr    aName// "Name"
0x58d4e  ldc.i4.s 0x17
0x58d50  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d55  dup
0x58d56  ldstr    aPagerendertype// "PageRenderType"
0x58d5b  ldc.i4.s 0x18
0x58d5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d62  dup
0x58d63  ldstr    aProperties// "Properties"
0x58d68  ldc.i4.s 0x19
0x58d6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d6f  dup
0x58d70  ldstr    aServerrelative_0// "ServerRelativePath"
0x58d75  ldc.i4.s 0x1A
0x58d77  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d7c  dup
0x58d7d  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x58d82  ldc.i4.s 0x1B
0x58d84  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d89  dup
0x58d8a  ldstr    aSiteid_0// "SiteId"
0x58d8f  ldc.i4.s 0x1C
0x58d91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58d96  dup
0x58d97  ldstr    aTimecreated// "TimeCreated"
0x58d9c  ldc.i4.s 0x1D
0x58d9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58da3  dup
0x58da4  ldstr    aTimelastmodifi// "TimeLastModified"
0x58da9  ldc.i4.s 0x1E
0x58dab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58db0  dup
0x58db1  ldstr    aTitle// "Title"
0x58db6  ldc.i4.s 0x1F
0x58db8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58dbd  dup
0x58dbe  ldstr    aUiversion// "UIVersion"
0x58dc3  ldc.i4.s 0x20
0x58dc5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58dca  dup
0x58dcb  ldstr    aUiversionlabel// "UIVersionLabel"
0x58dd0  ldc.i4.s 0x21
0x58dd2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58dd7  dup
0x58dd8  ldstr    aUniqueid_0// "UniqueId"
0x58ddd  ldc.i4.s 0x22
0x58ddf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58de4  dup
0x58de5  ldstr    aVersionevents// "VersionEvents"
0x58dea  ldc.i4.s 0x23
0x58dec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58df1  dup
0x58df2  ldstr    aVersions// "Versions"
0x58df7  ldc.i4.s 0x24
0x58df9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58dfe  dup
0x58dff  ldstr    aWebid_0// "WebId"
0x58e04  ldc.i4.s 0x25
0x58e06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58e0b  volatile.
0x58e0d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ff5-1
0x58e12  volatile.
0x58e14  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ff5-1
0x58e19  ldloc.1
0x58e1a  ldloca.s 2
0x58e1c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x58e21  brfalse  loc_591EB
0x58e26  ldloc.2
0x58e27  switch   loc_58EC9, loc_58EDC, loc_58EEF, loc_58F02, loc_58F15, loc_58F2D, loc_58F40, loc_58F53, loc_58F6B, loc_58F83, loc_58F96, loc_58FA9, loc_58FC1, loc_58FD4, loc_58FEC, loc_59004, loc_5901C, loc_5902F, loc_59042, loc_59055, loc_59068, loc_59080, loc_59098, loc_590AB, loc_590BE, loc_590D6, loc_590E9, loc_590FC, loc_5910F, loc_59127, loc_5913F, loc_59157, loc_5916A, loc_59182, loc_59195, loc_591AD, loc_591C0, loc_591D3
0x58ec4  br       loc_591EB
0x58ec9  ldarg.0
0x58eca  ldstr    aActivitycapabi// "ActivityCapabilities"
0x58ecf  ldarg.3
0x58ed0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58ed5  ldloc.0
0x58ed6  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityCapabilities [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ActivityCapabilities()
0x58edb  ret
0x58edc  ldarg.0
0x58edd  ldstr    aAuthor_0// "Author"
0x58ee2  ldarg.3
0x58ee3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58ee8  ldloc.0
0x58ee9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Author()
0x58eee  ret
0x58eef  ldarg.0
0x58ef0  ldstr    aCheckedoutbyus// "CheckedOutByUser"
0x58ef5  ldarg.3
0x58ef6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58efb  ldloc.0
0x58efc  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CheckedOutByUser()
0x58f01  ret
0x58f02  ldarg.0
0x58f03  ldstr    aCheckincomment_0// "CheckInComment"
0x58f08  ldarg.3
0x58f09  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f0e  ldloc.0
0x58f0f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CheckInComment()
0x58f14  ret
0x58f15  ldarg.0
0x58f16  ldstr    aCheckouttype// "CheckOutType"
0x58f1b  ldarg.3
0x58f1c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f21  ldloc.0
0x58f22  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFile/SPCheckOutType [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CheckOutType()
0x58f27  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPFile/SPCheckOutType
0x58f2c  ret
0x58f2d  ldarg.0
0x58f2e  ldstr    aClientactiviti_1// "ClientActivities"
0x58f33  ldarg.3
0x58f34  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f39  ldloc.0
0x58f3a  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ClientActivities()
0x58f3f  ret
0x58f40  ldarg.0
0x58f41  ldstr    aContenttag// "ContentTag"
0x58f46  ldarg.3
0x58f47  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f4c  ldloc.0
0x58f4d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ContentTag()
0x58f52  ret
0x58f53  ldarg.0
0x58f54  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x58f59  ldarg.3
0x58f5a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f5f  ldloc.0
0x58f60  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPCustomizedPageStatus [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CustomizedPageStatus()
0x58f65  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPCustomizedPageStatus
0x58f6a  ret
0x58f6b  ldarg.0
0x58f6c  ldstr    aListid_0// "ListId"
0x58f71  ldarg.3
0x58f72  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f77  ldloc.0
0x58f78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_DocumentLibraryId()
0x58f7d  box      [mscorlib]System.Guid
0x58f82  ret
0x58f83  ldarg.0
0x58f84  ldstr    aEffectiveinfor// "EffectiveInformationRightsManagementSet"...
0x58f89  ldarg.3
0x58f8a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f8f  ldloc.0
0x58f90  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_EffectiveInformationRightsManagementSettings()
0x58f95  ret
0x58f96  ldarg.0
0x58f97  ldstr    aEtag_0// "ETag"
0x58f9c  ldarg.3
0x58f9d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58fa2  ldloc.0
0x58fa3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ETag()
0x58fa8  ret
0x58fa9  ldarg.0
0x58faa  ldstr    aExists// "Exists"
0x58faf  ldarg.3
0x58fb0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58fb5  ldloc.0
0x58fb6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Exists()
0x58fbb  box      [mscorlib]System.Boolean
0x58fc0  ret
0x58fc1  ldarg.0
0x58fc2  ldstr    aInformationrig// "InformationRightsManagementSettings"
0x58fc7  ldarg.3
0x58fc8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58fcd  ldloc.0
0x58fce  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_InformationRightsManagementSettings()
0x58fd3  ret
0x58fd4  ldarg.0
0x58fd5  ldstr    aIrmenabled// "IrmEnabled"
0x58fda  ldarg.3
0x58fdb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58fe0  ldloc.0
0x58fe1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_IrmEnabled()
0x58fe6  box      [mscorlib]System.Boolean
0x58feb  ret
0x58fec  ldarg.0
0x58fed  ldstr    aLength// "Length"
  ... truncated ...
```
