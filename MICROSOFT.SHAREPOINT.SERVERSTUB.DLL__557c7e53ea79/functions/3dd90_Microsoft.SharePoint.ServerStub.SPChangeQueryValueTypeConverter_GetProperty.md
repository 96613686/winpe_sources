# Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::GetProperty

- ea: `0x3dd90`
- end: `0x3e1fa`
- name: `Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::GetProperty`
- size: `1130`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x3dd90`

## string_xrefs

- `0x3df71`: `Update`
- `0x3de2f`: `DeleteObject`
- `0x3df64`: `SystemUpdate`
- `0x3dee2`: `Rename`
- `0x3de0b`: `ChangeTokenEnd`
- `0x3de17`: `ChangeTokenStart`
- `0x3de87`: `GroupMembershipDelete`
- `0x3deef`: `RequireSecurityTrim`
- `0x3df16`: `RoleAssignmentDelete`
- `0x3df30`: `RoleDefinitionDelete`
- `0x3df3d`: `RoleDefinitionUpdate`
- `0x3df4a`: `SecurityPolicy`

## pseudocode

```c

```

## disassembly

```asm
0x3dd90  ldarg.3
0x3dd91  brtrue.s loc_3DD9E
0x3dd93  ldstr    aProxycontext// "proxyContext"
0x3dd98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3dd9d  throw
0x3dd9e  ldarg.1
0x3dd9f  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery
0x3dda4  stloc.0
0x3dda5  ldloc.0
0x3dda6  brtrue.s loc_3DDB3
0x3dda8  ldstr    aTarget// "target"
0x3ddad  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3ddb2  throw
0x3ddb3  ldarg.2
0x3ddb4  brtrue.s loc_3DDC1
0x3ddb6  ldstr    aPropname// "propName"
0x3ddbb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3ddc0  throw
0x3ddc1  ldarg.0
0x3ddc2  ldarg.2
0x3ddc3  ldarg.3
0x3ddc4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3ddc9  starg.s  2
0x3ddcb  ldarg.2
0x3ddcc  dup
0x3ddcd  stloc.1
0x3ddce  brfalse  loc_3E1F0
0x3ddd3  volatile.
0x3ddd5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b71-1
0x3ddda  brtrue   loc_3DFAB
0x3dddf  ldc.i4.s 0x23
0x3dde1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3dde6  dup
0x3dde7  ldstr    aActivity// "Activity"
0x3ddec  ldc.i4.0
0x3dded  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3ddf2  dup
0x3ddf3  ldstr    aAdd// "Add"
0x3ddf8  ldc.i4.1
0x3ddf9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3ddfe  dup
0x3ddff  ldstr    aAlert// "Alert"
0x3de04  ldc.i4.2
0x3de05  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de0a  dup
0x3de0b  ldstr    aChangetokenend// "ChangeTokenEnd"
0x3de10  ldc.i4.3
0x3de11  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de16  dup
0x3de17  ldstr    aChangetokensta// "ChangeTokenStart"
0x3de1c  ldc.i4.4
0x3de1d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de22  dup
0x3de23  ldstr    aContenttype// "ContentType"
0x3de28  ldc.i4.5
0x3de29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de2e  dup
0x3de2f  ldstr    aDeleteobject// "DeleteObject"
0x3de34  ldc.i4.6
0x3de35  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de3a  dup
0x3de3b  ldstr    aFetchlimit// "FetchLimit"
0x3de40  ldc.i4.7
0x3de41  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de46  dup
0x3de47  ldstr    aField// "Field"
0x3de4c  ldc.i4.8
0x3de4d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de52  dup
0x3de53  ldstr    aFile// "File"
0x3de58  ldc.i4.s 9
0x3de5a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de5f  dup
0x3de60  ldstr    aFolder// "Folder"
0x3de65  ldc.i4.s 0xA
0x3de67  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de6c  dup
0x3de6d  ldstr    aGroup// "Group"
0x3de72  ldc.i4.s 0xB
0x3de74  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de79  dup
0x3de7a  ldstr    aGroupmembershi// "GroupMembershipAdd"
0x3de7f  ldc.i4.s 0xC
0x3de81  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de86  dup
0x3de87  ldstr    aGroupmembershi_0// "GroupMembershipDelete"
0x3de8c  ldc.i4.s 0xD
0x3de8e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3de93  dup
0x3de94  ldstr    aItem_0// "Item"
0x3de99  ldc.i4.s 0xE
0x3de9b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3dea0  dup
0x3dea1  ldstr    aLatestfirst// "LatestFirst"
0x3dea6  ldc.i4.s 0xF
0x3dea8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3dead  dup
0x3deae  ldstr    aList// "List"
0x3deb3  ldc.i4.s 0x10
0x3deb5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3deba  dup
0x3debb  ldstr    aMove_0// "Move"
0x3dec0  ldc.i4.s 0x11
0x3dec2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3dec7  dup
0x3dec8  ldstr    aNavigation// "Navigation"
0x3decd  ldc.i4.s 0x12
0x3decf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3ded4  dup
0x3ded5  ldstr    aRecursiveall// "RecursiveAll"
0x3deda  ldc.i4.s 0x13
0x3dedc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3dee1  dup
0x3dee2  ldstr    aRename_0// "Rename"
0x3dee7  ldc.i4.s 0x14
0x3dee9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3deee  dup
0x3deef  ldstr    aRequiresecurit// "RequireSecurityTrim"
0x3def4  ldc.i4.s 0x15
0x3def6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3defb  dup
0x3defc  ldstr    aRestore_0// "Restore"
0x3df01  ldc.i4.s 0x16
0x3df03  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df08  dup
0x3df09  ldstr    aRoleassignment_0// "RoleAssignmentAdd"
0x3df0e  ldc.i4.s 0x17
0x3df10  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df15  dup
0x3df16  ldstr    aRoleassignment_1// "RoleAssignmentDelete"
0x3df1b  ldc.i4.s 0x18
0x3df1d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df22  dup
0x3df23  ldstr    aRoledefinition_0// "RoleDefinitionAdd"
0x3df28  ldc.i4.s 0x19
0x3df2a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df2f  dup
0x3df30  ldstr    aRoledefinition_1// "RoleDefinitionDelete"
0x3df35  ldc.i4.s 0x1A
0x3df37  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df3c  dup
0x3df3d  ldstr    aRoledefinition_2// "RoleDefinitionUpdate"
0x3df42  ldc.i4.s 0x1B
0x3df44  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df49  dup
0x3df4a  ldstr    aSecuritypolicy// "SecurityPolicy"
0x3df4f  ldc.i4.s 0x1C
0x3df51  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df56  dup
0x3df57  ldstr    aSite_0// "Site"
0x3df5c  ldc.i4.s 0x1D
0x3df5e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df63  dup
0x3df64  ldstr    aSystemupdate// "SystemUpdate"
0x3df69  ldc.i4.s 0x1E
0x3df6b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df70  dup
0x3df71  ldstr    aUpdate// "Update"
0x3df76  ldc.i4.s 0x1F
0x3df78  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df7d  dup
0x3df7e  ldstr    aUser// "User"
0x3df83  ldc.i4.s 0x20
0x3df85  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df8a  dup
0x3df8b  ldstr    aView// "View"
0x3df90  ldc.i4.s 0x21
0x3df92  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3df97  dup
0x3df98  ldstr    aWeb_0// "Web"
0x3df9d  ldc.i4.s 0x22
0x3df9f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3dfa4  volatile.
0x3dfa6  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b71-1
0x3dfab  volatile.
0x3dfad  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b71-1
0x3dfb2  ldloc.1
0x3dfb3  ldloca.s 2
0x3dfb5  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x3dfba  brfalse  loc_3E1F0
0x3dfbf  ldloc.2
0x3dfc0  switch   loc_3E056, loc_3E062, loc_3E06E, loc_3E07A, loc_3E081, loc_3E088, loc_3E094, loc_3E0A0, loc_3E0AC, loc_3E0B8, loc_3E0C4, loc_3E0D0, loc_3E0DC, loc_3E0E8, loc_3E0F4, loc_3E100, loc_3E10C, loc_3E118, loc_3E124, loc_3E130, loc_3E13C, loc_3E148, loc_3E154, loc_3E160, loc_3E16C, loc_3E178, loc_3E184, loc_3E190, loc_3E19C, loc_3E1A8, loc_3E1B4, loc_3E1C0, loc_3E1CC, loc_3E1D8, loc_3E1E4
0x3e051  br       loc_3E1F0
0x3e056  ldloc.0
0x3e057  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Activity()
0x3e05c  box      [mscorlib]System.Boolean
0x3e061  ret
0x3e062  ldloc.0
0x3e063  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Add()
0x3e068  box      [mscorlib]System.Boolean
0x3e06d  ret
0x3e06e  ldloc.0
0x3e06f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Alert()
0x3e074  box      [mscorlib]System.Boolean
0x3e079  ret
0x3e07a  ldloc.0
0x3e07b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_ChangeTokenEnd()
0x3e080  ret
0x3e081  ldloc.0
0x3e082  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_ChangeTokenStart()
0x3e087  ret
0x3e088  ldloc.0
0x3e089  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_ContentType()
0x3e08e  box      [mscorlib]System.Boolean
0x3e093  ret
0x3e094  ldloc.0
0x3e095  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Delete()
0x3e09a  box      [mscorlib]System.Boolean
0x3e09f  ret
0x3e0a0  ldloc.0
0x3e0a1  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_FetchLimit()
0x3e0a6  box      [mscorlib]System.Int64
0x3e0ab  ret
0x3e0ac  ldloc.0
0x3e0ad  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Field()
0x3e0b2  box      [mscorlib]System.Boolean
0x3e0b7  ret
0x3e0b8  ldloc.0
0x3e0b9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_File()
0x3e0be  box      [mscorlib]System.Boolean
0x3e0c3  ret
0x3e0c4  ldloc.0
0x3e0c5  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Folder()
0x3e0ca  box      [mscorlib]System.Boolean
0x3e0cf  ret
0x3e0d0  ldloc.0
0x3e0d1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Group()
0x3e0d6  box      [mscorlib]System.Boolean
0x3e0db  ret
0x3e0dc  ldloc.0
0x3e0dd  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_GroupMembershipAdd()
0x3e0e2  box      [mscorlib]System.Boolean
0x3e0e7  ret
0x3e0e8  ldloc.0
0x3e0e9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_GroupMembershipDelete()
0x3e0ee  box      [mscorlib]System.Boolean
0x3e0f3  ret
0x3e0f4  ldloc.0
0x3e0f5  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Item()
0x3e0fa  box      [mscorlib]System.Boolean
0x3e0ff  ret
0x3e100  ldloc.0
0x3e101  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_LatestFirst()
0x3e106  box      [mscorlib]System.Boolean
0x3e10b  ret
0x3e10c  ldloc.0
0x3e10d  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_List()
0x3e112  box      [mscorlib]System.Boolean
0x3e117  ret
0x3e118  ldloc.0
0x3e119  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Move()
0x3e11e  box      [mscorlib]System.Boolean
0x3e123  ret
0x3e124  ldloc.0
0x3e125  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Navigation()
0x3e12a  box      [mscorlib]System.Boolean
0x3e12f  ret
0x3e130  ldloc.0
0x3e131  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RecursiveAll()
0x3e136  box      [mscorlib]System.Boolean
0x3e13b  ret
0x3e13c  ldloc.0
0x3e13d  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Rename()
0x3e142  box      [mscorlib]System.Boolean
0x3e147  ret
0x3e148  ldloc.0
0x3e149  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RequireSecurityTrim()
0x3e14e  box      [mscorlib]System.Boolean
0x3e153  ret
0x3e154  ldloc.0
0x3e155  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Restore()
0x3e15a  box      [mscorlib]System.Boolean
0x3e15f  ret
0x3e160  ldloc.0
0x3e161  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleAssignmentAdd()
0x3e166  box      [mscorlib]System.Boolean
0x3e16b  ret
0x3e16c  ldloc.0
0x3e16d  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleAssignmentDelete()
0x3e172  box      [mscorlib]System.Boolean
0x3e177  ret
0x3e178  ldloc.0
0x3e179  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleDefinitionAdd()
0x3e17e  box      [mscorlib]System.Boolean
0x3e183  ret
0x3e184  ldloc.0
0x3e185  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleDefinitionDelete()
0x3e18a  box      [mscorlib]System.Boolean
0x3e18f  ret
0x3e190  ldloc.0
0x3e191  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleDefinitionUpdate()
0x3e196  box      [mscorlib]System.Boolean
0x3e19b  ret
0x3e19c  ldloc.0
0x3e19d  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_SecurityPolicy()
0x3e1a2  box      [mscorlib]System.Boolean
0x3e1a7  ret
0x3e1a8  ldloc.0
0x3e1a9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Site()
0x3e1ae  box      [mscorlib]System.Boolean
  ... truncated ...
```
