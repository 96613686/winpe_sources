# Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetProperty

- ea: `0xa070`
- end: `0xa48a`
- name: `Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetProperty`
- size: `1050`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x10d0`
- `0xa070`

## string_xrefs

- `0xa0df`: `CommentsDisabled`
- `0xa2b3`: `CommentsDisabled`
- `0xa0eb`: `CommentsDisabledScope`
- `0xa2cb`: `CommentsDisabledScope`
- `0xa1cf`: `ServerRedirectedEmbedUri`
- `0xa435`: `ServerRedirectedEmbedUri`

## pseudocode

```c

```

## disassembly

```asm
0xa070  ldarg.2
0xa071  brtrue.s loc_A07E
0xa073  ldstr    aPropname// "propName"
0xa078  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa07d  throw
0xa07e  ldarg.3
0xa07f  brtrue.s loc_A08C
0xa081  ldstr    aProxycontext// "proxyContext"
0xa086  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa08b  throw
0xa08c  ldarg.1
0xa08d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0xa092  stloc.0
0xa093  ldloc.0
0xa094  brtrue.s loc_A0A1
0xa096  ldstr    aTarget// "target"
0xa09b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa0a0  throw
0xa0a1  ldarg.0
0xa0a2  ldarg.2
0xa0a3  ldarg.3
0xa0a4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa0a9  starg.s  2
0xa0ab  ldarg.2
0xa0ac  dup
0xa0ad  stloc.1
0xa0ae  brfalse  loc_A480
0xa0b3  volatile.
0xa0b5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000135-1
0xa0ba  brtrue   loc_A209
0xa0bf  ldc.i4.s 0x19
0xa0c1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xa0c6  dup
0xa0c7  ldstr    aActivities// "Activities"
0xa0cc  ldc.i4.0
0xa0cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa0d2  dup
0xa0d3  ldstr    aAttachmentfile// "AttachmentFiles"
0xa0d8  ldc.i4.1
0xa0d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa0de  dup
0xa0df  ldstr    aCommentsdisabl// "CommentsDisabled"
0xa0e4  ldc.i4.2
0xa0e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa0ea  dup
0xa0eb  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
0xa0f0  ldc.i4.3
0xa0f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa0f6  dup
0xa0f7  ldstr    aContenttype// "ContentType"
0xa0fc  ldc.i4.4
0xa0fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa102  dup
0xa103  ldstr    aDisplayname// "DisplayName"
0xa108  ldc.i4.5
0xa109  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa10e  dup
0xa10f  ldstr    aGetdlppolicyti// "GetDlpPolicyTip"
0xa114  ldc.i4.6
0xa115  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa11a  dup
0xa11b  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0xa120  ldc.i4.7
0xa121  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa126  dup
0xa127  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0xa12c  ldc.i4.8
0xa12d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa132  dup
0xa133  ldstr    aFieldvaluesash// "FieldValuesAsHtml"
0xa138  ldc.i4.s 9
0xa13a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa13f  dup
0xa140  ldstr    aFieldvaluesast// "FieldValuesAsText"
0xa145  ldc.i4.s 0xA
0xa147  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa14c  dup
0xa14d  ldstr    aFieldvaluesfor// "FieldValuesForEdit"
0xa152  ldc.i4.s 0xB
0xa154  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa159  dup
0xa15a  ldstr    aFile// "File"
0xa15f  ldc.i4.s 0xC
0xa161  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa166  dup
0xa167  ldstr    aFilesystemobje// "FileSystemObjectType"
0xa16c  ldc.i4.s 0xD
0xa16e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa173  dup
0xa174  ldstr    aFolder// "Folder"
0xa179  ldc.i4.s 0xE
0xa17b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa180  dup
0xa181  ldstr    aHasuniquerolea// "HasUniqueRoleAssignments"
0xa186  ldc.i4.s 0xF
0xa188  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa18d  dup
0xa18e  ldstr    aIconoverlay// "IconOverlay"
0xa193  ldc.i4.s 0x10
0xa195  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa19a  dup
0xa19b  ldstr    aId_0// "Id"
0xa1a0  ldc.i4.s 0x11
0xa1a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1a7  dup
0xa1a8  ldstr    aLikedbyinforma// "LikedByInformation"
0xa1ad  ldc.i4.s 0x12
0xa1af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1b4  dup
0xa1b5  ldstr    aParentlist// "ParentList"
0xa1ba  ldc.i4.s 0x13
0xa1bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1c1  dup
0xa1c2  ldstr    aProperties// "Properties"
0xa1c7  ldc.i4.s 0x14
0xa1c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1ce  dup
0xa1cf  ldstr    aServerredirect// "ServerRedirectedEmbedUri"
0xa1d4  ldc.i4.s 0x15
0xa1d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1db  dup
0xa1dc  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xa1e1  ldc.i4.s 0x16
0xa1e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1e8  dup
0xa1e9  ldstr    aClientTitle// "Client_Title"
0xa1ee  ldc.i4.s 0x17
0xa1f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1f5  dup
0xa1f6  ldstr    aVersions// "Versions"
0xa1fb  ldc.i4.s 0x18
0xa1fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa202  volatile.
0xa204  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000135-1
0xa209  volatile.
0xa20b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000135-1
0xa210  ldloc.1
0xa211  ldloca.s 2
0xa213  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xa218  brfalse  loc_A480
0xa21d  ldloc.2
0xa21e  switch   loc_A28C, loc_A29F, loc_A2B2, loc_A2CA, loc_A2E2, loc_A2F5, loc_A308, loc_A31B, loc_A32E, loc_A341, loc_A354, loc_A367, loc_A37A, loc_A38D, loc_A3A5, loc_A3B8, loc_A3D0, loc_A3E3, loc_A3FB, loc_A40E, loc_A421, loc_A434, loc_A447, loc_A45A, loc_A46D
0xa287  br       loc_A480
0xa28c  ldarg.0
0xa28d  ldstr    aActivities// "Activities"
0xa292  ldarg.3
0xa293  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa298  ldloc.0
0xa299  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_Activities()
0xa29e  ret
0xa29f  ldarg.0
0xa2a0  ldstr    aAttachmentfile// "AttachmentFiles"
0xa2a5  ldarg.3
0xa2a6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2ab  ldloc.0
0xa2ac  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachmentCollection_Client [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_Attachments_Client()
0xa2b1  ret
0xa2b2  ldarg.0
0xa2b3  ldstr    aCommentsdisabl// "CommentsDisabled"
0xa2b8  ldarg.3
0xa2b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2be  ldloc.0
0xa2bf  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_CommentsDisabled()
0xa2c4  box      [mscorlib]System.Boolean
0xa2c9  ret
0xa2ca  ldarg.0
0xa2cb  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
0xa2d0  ldarg.3
0xa2d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2d6  ldloc.0
0xa2d7  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Comments.SPCommentsDisabledScope [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_CommentsDisabledScope()
0xa2dc  box      [Microsoft.SharePoint]Microsoft.SharePoint.Comments.SPCommentsDisabledScope
0xa2e1  ret
0xa2e2  ldarg.0
0xa2e3  ldstr    aContenttype// "ContentType"
0xa2e8  ldarg.3
0xa2e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2ee  ldloc.0
0xa2ef  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_ContentType()
0xa2f4  ret
0xa2f5  ldarg.0
0xa2f6  ldstr    aDisplayname// "DisplayName"
0xa2fb  ldarg.3
0xa2fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa301  ldloc.0
0xa302  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_DisplayName()
0xa307  ret
0xa308  ldarg.0
0xa309  ldstr    aGetdlppolicyti// "GetDlpPolicyTip"
0xa30e  ldarg.3
0xa30f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa314  ldloc.0
0xa315  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPDlpPolicyTip [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_DlpPolicyTip()
0xa31a  ret
0xa31b  ldarg.0
0xa31c  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0xa321  ldarg.3
0xa322  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa327  ldloc.0
0xa328  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_EffectiveBasePermissions_Client()
0xa32d  ret
0xa32e  ldarg.0
0xa32f  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0xa334  ldarg.3
0xa335  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa33a  ldloc.0
0xa33b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_EffectiveBasePermissionsForUI_Client()
0xa340  ret
0xa341  ldarg.0
0xa342  ldstr    aFieldvaluesash// "FieldValuesAsHtml"
0xa347  ldarg.3
0xa348  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa34d  ldloc.0
0xa34e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldStringValues [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_FieldValuesAsHtml_Client()
0xa353  ret
0xa354  ldarg.0
0xa355  ldstr    aFieldvaluesast// "FieldValuesAsText"
0xa35a  ldarg.3
0xa35b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa360  ldloc.0
0xa361  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldStringValues [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_FieldValuesAsText_Client()
0xa366  ret
0xa367  ldarg.0
0xa368  ldstr    aFieldvaluesfor// "FieldValuesForEdit"
0xa36d  ldarg.3
0xa36e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa373  ldloc.0
0xa374  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldStringValues [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_FieldValuesForEdit_Client()
0xa379  ret
0xa37a  ldarg.0
0xa37b  ldstr    aFile// "File"
0xa380  ldarg.3
0xa381  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa386  ldloc.0
0xa387  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_File()
0xa38c  ret
0xa38d  ldarg.0
0xa38e  ldstr    aFilesystemobje// "FileSystemObjectType"
0xa393  ldarg.3
0xa394  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa399  ldloc.0
0xa39a  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFileSystemObjectType [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_FileSystemObjectType()
0xa39f  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPFileSystemObjectType
0xa3a4  ret
0xa3a5  ldarg.0
0xa3a6  ldstr    aFolder// "Folder"
0xa3ab  ldarg.3
0xa3ac  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3b1  ldloc.0
0xa3b2  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_Folder()
0xa3b7  ret
0xa3b8  ldarg.0
0xa3b9  ldstr    aHasuniquerolea// "HasUniqueRoleAssignments"
0xa3be  ldarg.3
0xa3bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3c4  ldloc.0
0xa3c5  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurableObject::get_HasUniqueRoleAssignments()
0xa3ca  box      [mscorlib]System.Boolean
0xa3cf  ret
0xa3d0  ldarg.0
0xa3d1  ldstr    aIconoverlay// "IconOverlay"
0xa3d6  ldarg.3
0xa3d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3dc  ldloc.0
0xa3dd  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_IconOverlay()
0xa3e2  ret
0xa3e3  ldarg.0
0xa3e4  ldstr    aId_0// "Id"
0xa3e9  ldarg.3
0xa3ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3ef  ldloc.0
0xa3f0  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPItem::get_ID()
0xa3f5  box      [mscorlib]System.Int32
0xa3fa  ret
0xa3fb  ldarg.0
0xa3fc  ldstr    aLikedbyinforma// "LikedByInformation"
0xa401  ldarg.3
0xa402  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa407  ldloc.0
0xa408  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Likes.LikedByInformation [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_LikedByInformation_Client()
0xa40d  ret
0xa40e  ldarg.0
0xa40f  ldstr    aParentlist// "ParentList"
0xa414  ldarg.3
0xa415  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa41a  ldloc.0
0xa41b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_ParentList()
0xa420  ret
0xa421  ldarg.0
0xa422  ldstr    aProperties// "Properties"
0xa427  ldarg.3
0xa428  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa42d  ldloc.0
0xa42e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPPropertyValues [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_Properties_Client()
0xa433  ret
0xa434  ldarg.0
0xa435  ldstr    aServerredirect// "ServerRedirectedEmbedUri"
0xa43a  ldarg.3
0xa43b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa440  ldloc.0
  ... truncated ...
```
