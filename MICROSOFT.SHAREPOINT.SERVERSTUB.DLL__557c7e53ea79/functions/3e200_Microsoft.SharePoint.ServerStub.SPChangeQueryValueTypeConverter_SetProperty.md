# Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::SetProperty

- ea: `0x3e200`
- end: `0x3e6a9`
- name: `Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::SetProperty`
- size: `1193`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x3e200`

## string_xrefs

- `0x3e3f1`: `Update`
- `0x3e2af`: `DeleteObject`
- `0x3e3e4`: `SystemUpdate`
- `0x3e362`: `Rename`
- `0x3e28b`: `ChangeTokenEnd`
- `0x3e297`: `ChangeTokenStart`
- `0x3e307`: `GroupMembershipDelete`
- `0x3e36f`: `RequireSecurityTrim`
- `0x3e396`: `RoleAssignmentDelete`
- `0x3e3b0`: `RoleDefinitionDelete`
- `0x3e3bd`: `RoleDefinitionUpdate`
- `0x3e3ca`: `SecurityPolicy`

## pseudocode

```c

```

## disassembly

```asm
0x3e200  ldarg.s  4
0x3e202  brtrue.s loc_3E20F
0x3e204  ldstr    aProxycontext// "proxyContext"
0x3e209  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3e20e  throw
0x3e20f  ldarg.1
0x3e210  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery
0x3e215  stloc.0
0x3e216  ldloc.0
0x3e217  brtrue.s loc_3E224
0x3e219  ldstr    aTarget// "target"
0x3e21e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3e223  throw
0x3e224  ldarg.2
0x3e225  brtrue.s loc_3E232
0x3e227  ldstr    aPropname// "propName"
0x3e22c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3e231  throw
0x3e232  ldarg.3
0x3e233  brtrue.s loc_3E240
0x3e235  ldstr    aPropvalue// "propValue"
0x3e23a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3e23f  throw
0x3e240  ldarg.0
0x3e241  ldarg.2
0x3e242  ldarg.s  4
0x3e244  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e249  starg.s  2
0x3e24b  ldarg.2
0x3e24c  dup
0x3e24d  stloc.1
0x3e24e  brfalse  loc_3E69D
0x3e253  volatile.
0x3e255  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b72-1
0x3e25a  brtrue   loc_3E42B
0x3e25f  ldc.i4.s 0x23
0x3e261  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3e266  dup
0x3e267  ldstr    aActivity// "Activity"
0x3e26c  ldc.i4.0
0x3e26d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e272  dup
0x3e273  ldstr    aAdd// "Add"
0x3e278  ldc.i4.1
0x3e279  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e27e  dup
0x3e27f  ldstr    aAlert// "Alert"
0x3e284  ldc.i4.2
0x3e285  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e28a  dup
0x3e28b  ldstr    aChangetokenend// "ChangeTokenEnd"
0x3e290  ldc.i4.3
0x3e291  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e296  dup
0x3e297  ldstr    aChangetokensta// "ChangeTokenStart"
0x3e29c  ldc.i4.4
0x3e29d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2a2  dup
0x3e2a3  ldstr    aContenttype// "ContentType"
0x3e2a8  ldc.i4.5
0x3e2a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2ae  dup
0x3e2af  ldstr    aDeleteobject// "DeleteObject"
0x3e2b4  ldc.i4.6
0x3e2b5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2ba  dup
0x3e2bb  ldstr    aFetchlimit// "FetchLimit"
0x3e2c0  ldc.i4.7
0x3e2c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2c6  dup
0x3e2c7  ldstr    aField// "Field"
0x3e2cc  ldc.i4.8
0x3e2cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2d2  dup
0x3e2d3  ldstr    aFile// "File"
0x3e2d8  ldc.i4.s 9
0x3e2da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2df  dup
0x3e2e0  ldstr    aFolder// "Folder"
0x3e2e5  ldc.i4.s 0xA
0x3e2e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2ec  dup
0x3e2ed  ldstr    aGroup// "Group"
0x3e2f2  ldc.i4.s 0xB
0x3e2f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e2f9  dup
0x3e2fa  ldstr    aGroupmembershi// "GroupMembershipAdd"
0x3e2ff  ldc.i4.s 0xC
0x3e301  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e306  dup
0x3e307  ldstr    aGroupmembershi_0// "GroupMembershipDelete"
0x3e30c  ldc.i4.s 0xD
0x3e30e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e313  dup
0x3e314  ldstr    aItem_0// "Item"
0x3e319  ldc.i4.s 0xE
0x3e31b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e320  dup
0x3e321  ldstr    aLatestfirst// "LatestFirst"
0x3e326  ldc.i4.s 0xF
0x3e328  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e32d  dup
0x3e32e  ldstr    aList// "List"
0x3e333  ldc.i4.s 0x10
0x3e335  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e33a  dup
0x3e33b  ldstr    aMove_0// "Move"
0x3e340  ldc.i4.s 0x11
0x3e342  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e347  dup
0x3e348  ldstr    aNavigation// "Navigation"
0x3e34d  ldc.i4.s 0x12
0x3e34f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e354  dup
0x3e355  ldstr    aRecursiveall// "RecursiveAll"
0x3e35a  ldc.i4.s 0x13
0x3e35c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e361  dup
0x3e362  ldstr    aRename_0// "Rename"
0x3e367  ldc.i4.s 0x14
0x3e369  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e36e  dup
0x3e36f  ldstr    aRequiresecurit// "RequireSecurityTrim"
0x3e374  ldc.i4.s 0x15
0x3e376  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e37b  dup
0x3e37c  ldstr    aRestore_0// "Restore"
0x3e381  ldc.i4.s 0x16
0x3e383  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e388  dup
0x3e389  ldstr    aRoleassignment_0// "RoleAssignmentAdd"
0x3e38e  ldc.i4.s 0x17
0x3e390  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e395  dup
0x3e396  ldstr    aRoleassignment_1// "RoleAssignmentDelete"
0x3e39b  ldc.i4.s 0x18
0x3e39d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3a2  dup
0x3e3a3  ldstr    aRoledefinition_0// "RoleDefinitionAdd"
0x3e3a8  ldc.i4.s 0x19
0x3e3aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3af  dup
0x3e3b0  ldstr    aRoledefinition_1// "RoleDefinitionDelete"
0x3e3b5  ldc.i4.s 0x1A
0x3e3b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3bc  dup
0x3e3bd  ldstr    aRoledefinition_2// "RoleDefinitionUpdate"
0x3e3c2  ldc.i4.s 0x1B
0x3e3c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3c9  dup
0x3e3ca  ldstr    aSecuritypolicy// "SecurityPolicy"
0x3e3cf  ldc.i4.s 0x1C
0x3e3d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3d6  dup
0x3e3d7  ldstr    aSite_0// "Site"
0x3e3dc  ldc.i4.s 0x1D
0x3e3de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3e3  dup
0x3e3e4  ldstr    aSystemupdate// "SystemUpdate"
0x3e3e9  ldc.i4.s 0x1E
0x3e3eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3f0  dup
0x3e3f1  ldstr    aUpdate// "Update"
0x3e3f6  ldc.i4.s 0x1F
0x3e3f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e3fd  dup
0x3e3fe  ldstr    aUser// "User"
0x3e403  ldc.i4.s 0x20
0x3e405  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e40a  dup
0x3e40b  ldstr    aView// "View"
0x3e410  ldc.i4.s 0x21
0x3e412  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e417  dup
0x3e418  ldstr    aWeb_0// "Web"
0x3e41d  ldc.i4.s 0x22
0x3e41f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3e424  volatile.
0x3e426  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b72-1
0x3e42b  volatile.
0x3e42d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b72-1
0x3e432  ldloc.1
0x3e433  ldloca.s 2
0x3e435  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x3e43a  brfalse  loc_3E69D
0x3e43f  ldloc.2
0x3e440  switch   loc_3E4D6, loc_3E4E3, loc_3E4F0, loc_3E4FD, loc_3E50A, loc_3E517, loc_3E524, loc_3E531, loc_3E53E, loc_3E54B, loc_3E558, loc_3E565, loc_3E572, loc_3E57F, loc_3E58C, loc_3E599, loc_3E5A6, loc_3E5B3, loc_3E5C0, loc_3E5CD, loc_3E5DA, loc_3E5E7, loc_3E5F4, loc_3E601, loc_3E60E, loc_3E61B, loc_3E628, loc_3E635, loc_3E642, loc_3E64F, loc_3E65C, loc_3E669, loc_3E676, loc_3E683, loc_3E690
0x3e4d1  br       loc_3E69D
0x3e4d6  ldloc.0
0x3e4d7  ldarg.3
0x3e4d8  callvirt T0x2B00000A
0x3e4dd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Activity(bool)
0x3e4e2  ret
0x3e4e3  ldloc.0
0x3e4e4  ldarg.3
0x3e4e5  callvirt T0x2B00000A
0x3e4ea  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Add(bool)
0x3e4ef  ret
0x3e4f0  ldloc.0
0x3e4f1  ldarg.3
0x3e4f2  callvirt T0x2B00000A
0x3e4f7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Alert(bool)
0x3e4fc  ret
0x3e4fd  ldloc.0
0x3e4fe  ldarg.3
0x3e4ff  callvirt T0x2B00015B
0x3e504  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ChangeTokenEnd(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x3e509  ret
0x3e50a  ldloc.0
0x3e50b  ldarg.3
0x3e50c  callvirt T0x2B00015B
0x3e511  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ChangeTokenStart(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x3e516  ret
0x3e517  ldloc.0
0x3e518  ldarg.3
0x3e519  callvirt T0x2B00000A
0x3e51e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ContentType(bool)
0x3e523  ret
0x3e524  ldloc.0
0x3e525  ldarg.3
0x3e526  callvirt T0x2B00000A
0x3e52b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Delete(bool)
0x3e530  ret
0x3e531  ldloc.0
0x3e532  ldarg.3
0x3e533  callvirt T0x2B0000D5
0x3e538  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_FetchLimit(int64)
0x3e53d  ret
0x3e53e  ldloc.0
0x3e53f  ldarg.3
0x3e540  callvirt T0x2B00000A
0x3e545  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Field(bool)
0x3e54a  ret
0x3e54b  ldloc.0
0x3e54c  ldarg.3
0x3e54d  callvirt T0x2B00000A
0x3e552  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_File(bool)
0x3e557  ret
0x3e558  ldloc.0
0x3e559  ldarg.3
0x3e55a  callvirt T0x2B00000A
0x3e55f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Folder(bool)
0x3e564  ret
0x3e565  ldloc.0
0x3e566  ldarg.3
0x3e567  callvirt T0x2B00000A
0x3e56c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Group(bool)
0x3e571  ret
0x3e572  ldloc.0
0x3e573  ldarg.3
0x3e574  callvirt T0x2B00000A
0x3e579  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_GroupMembershipAdd(bool)
0x3e57e  ret
0x3e57f  ldloc.0
0x3e580  ldarg.3
0x3e581  callvirt T0x2B00000A
0x3e586  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_GroupMembershipDelete(bool)
0x3e58b  ret
0x3e58c  ldloc.0
0x3e58d  ldarg.3
0x3e58e  callvirt T0x2B00000A
0x3e593  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Item(bool)
0x3e598  ret
0x3e599  ldloc.0
0x3e59a  ldarg.3
0x3e59b  callvirt T0x2B00000A
0x3e5a0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_LatestFirst(bool)
0x3e5a5  ret
0x3e5a6  ldloc.0
0x3e5a7  ldarg.3
0x3e5a8  callvirt T0x2B00000A
0x3e5ad  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_List(bool)
0x3e5b2  ret
0x3e5b3  ldloc.0
0x3e5b4  ldarg.3
0x3e5b5  callvirt T0x2B00000A
0x3e5ba  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Move(bool)
0x3e5bf  ret
0x3e5c0  ldloc.0
0x3e5c1  ldarg.3
0x3e5c2  callvirt T0x2B00000A
0x3e5c7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Navigation(bool)
0x3e5cc  ret
0x3e5cd  ldloc.0
0x3e5ce  ldarg.3
0x3e5cf  callvirt T0x2B00000A
0x3e5d4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_RecursiveAll(bool)
0x3e5d9  ret
0x3e5da  ldloc.0
0x3e5db  ldarg.3
0x3e5dc  callvirt T0x2B00000A
0x3e5e1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Rename(bool)
0x3e5e6  ret
0x3e5e7  ldloc.0
0x3e5e8  ldarg.3
0x3e5e9  callvirt T0x2B00000A
0x3e5ee  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_RequireSecurityTrim(bool)
0x3e5f3  ret
0x3e5f4  ldloc.0
0x3e5f5  ldarg.3
  ... truncated ...
```
