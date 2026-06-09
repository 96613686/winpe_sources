# Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::InitFromXml

- ea: `0x3d810`
- end: `0x3dd6c`
- name: `Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::InitFromXml`
- size: `1372`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x3d810`

## string_xrefs

- `0x3da07`: `Update`
- `0x3d8c5`: `DeleteObject`
- `0x3d9fa`: `SystemUpdate`
- `0x3d978`: `Rename`
- `0x3d8a1`: `ChangeTokenEnd`
- `0x3d8ad`: `ChangeTokenStart`
- `0x3d91d`: `GroupMembershipDelete`
- `0x3d985`: `RequireSecurityTrim`
- `0x3d9ac`: `RoleAssignmentDelete`
- `0x3d9c6`: `RoleDefinitionDelete`
- `0x3d9d3`: `RoleDefinitionUpdate`
- `0x3d9e0`: `SecurityPolicy`

## pseudocode

```c

```

## disassembly

```asm
0x3d810  ldarg.0
0x3d811  ldarg.1
0x3d812  ldarg.2
0x3d813  ldarg.3
0x3d814  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3d819  starg.s  1
0x3d81b  ldarg.1
0x3d81c  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery
0x3d821  stloc.0
0x3d822  ldloc.0
0x3d823  brfalse  loc_3DD6A
0x3d828  ldarg.2
0x3d829  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x3d82e  stloc.s  4
0x3d830  br       loc_3DD47
0x3d835  ldloc.s  4
0x3d837  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3d83c  castclass [System.Xml]System.Xml.XmlNode
0x3d841  stloc.1
0x3d842  ldloc.1
0x3d843  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3d848  ldstr    aName// "Name"
0x3d84d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3d852  stloc.2
0x3d853  ldloc.2
0x3d854  brfalse  loc_3DD47
0x3d859  ldloc.2
0x3d85a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3d85f  stloc.3
0x3d860  ldloc.3
0x3d861  dup
0x3d862  stloc.s  5
0x3d864  brfalse  loc_3DD47
0x3d869  volatile.
0x3d86b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b6f-1
0x3d870  brtrue   loc_3DA41
0x3d875  ldc.i4.s 0x23
0x3d877  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3d87c  dup
0x3d87d  ldstr    aActivity// "Activity"
0x3d882  ldc.i4.0
0x3d883  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d888  dup
0x3d889  ldstr    aAdd// "Add"
0x3d88e  ldc.i4.1
0x3d88f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d894  dup
0x3d895  ldstr    aAlert// "Alert"
0x3d89a  ldc.i4.2
0x3d89b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8a0  dup
0x3d8a1  ldstr    aChangetokenend// "ChangeTokenEnd"
0x3d8a6  ldc.i4.3
0x3d8a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8ac  dup
0x3d8ad  ldstr    aChangetokensta// "ChangeTokenStart"
0x3d8b2  ldc.i4.4
0x3d8b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8b8  dup
0x3d8b9  ldstr    aContenttype// "ContentType"
0x3d8be  ldc.i4.5
0x3d8bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8c4  dup
0x3d8c5  ldstr    aDeleteobject// "DeleteObject"
0x3d8ca  ldc.i4.6
0x3d8cb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8d0  dup
0x3d8d1  ldstr    aFetchlimit// "FetchLimit"
0x3d8d6  ldc.i4.7
0x3d8d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8dc  dup
0x3d8dd  ldstr    aField// "Field"
0x3d8e2  ldc.i4.8
0x3d8e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8e8  dup
0x3d8e9  ldstr    aFile// "File"
0x3d8ee  ldc.i4.s 9
0x3d8f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d8f5  dup
0x3d8f6  ldstr    aFolder// "Folder"
0x3d8fb  ldc.i4.s 0xA
0x3d8fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d902  dup
0x3d903  ldstr    aGroup// "Group"
0x3d908  ldc.i4.s 0xB
0x3d90a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d90f  dup
0x3d910  ldstr    aGroupmembershi// "GroupMembershipAdd"
0x3d915  ldc.i4.s 0xC
0x3d917  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d91c  dup
0x3d91d  ldstr    aGroupmembershi_0// "GroupMembershipDelete"
0x3d922  ldc.i4.s 0xD
0x3d924  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d929  dup
0x3d92a  ldstr    aItem_0// "Item"
0x3d92f  ldc.i4.s 0xE
0x3d931  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d936  dup
0x3d937  ldstr    aLatestfirst// "LatestFirst"
0x3d93c  ldc.i4.s 0xF
0x3d93e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d943  dup
0x3d944  ldstr    aList// "List"
0x3d949  ldc.i4.s 0x10
0x3d94b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d950  dup
0x3d951  ldstr    aMove_0// "Move"
0x3d956  ldc.i4.s 0x11
0x3d958  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d95d  dup
0x3d95e  ldstr    aNavigation// "Navigation"
0x3d963  ldc.i4.s 0x12
0x3d965  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d96a  dup
0x3d96b  ldstr    aRecursiveall// "RecursiveAll"
0x3d970  ldc.i4.s 0x13
0x3d972  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d977  dup
0x3d978  ldstr    aRename_0// "Rename"
0x3d97d  ldc.i4.s 0x14
0x3d97f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d984  dup
0x3d985  ldstr    aRequiresecurit// "RequireSecurityTrim"
0x3d98a  ldc.i4.s 0x15
0x3d98c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d991  dup
0x3d992  ldstr    aRestore_0// "Restore"
0x3d997  ldc.i4.s 0x16
0x3d999  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d99e  dup
0x3d99f  ldstr    aRoleassignment_0// "RoleAssignmentAdd"
0x3d9a4  ldc.i4.s 0x17
0x3d9a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d9ab  dup
0x3d9ac  ldstr    aRoleassignment_1// "RoleAssignmentDelete"
0x3d9b1  ldc.i4.s 0x18
0x3d9b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d9b8  dup
0x3d9b9  ldstr    aRoledefinition_0// "RoleDefinitionAdd"
0x3d9be  ldc.i4.s 0x19
0x3d9c0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d9c5  dup
0x3d9c6  ldstr    aRoledefinition_1// "RoleDefinitionDelete"
0x3d9cb  ldc.i4.s 0x1A
0x3d9cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d9d2  dup
0x3d9d3  ldstr    aRoledefinition_2// "RoleDefinitionUpdate"
0x3d9d8  ldc.i4.s 0x1B
0x3d9da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d9df  dup
0x3d9e0  ldstr    aSecuritypolicy// "SecurityPolicy"
0x3d9e5  ldc.i4.s 0x1C
0x3d9e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d9ec  dup
0x3d9ed  ldstr    aSite_0// "Site"
0x3d9f2  ldc.i4.s 0x1D
0x3d9f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3d9f9  dup
0x3d9fa  ldstr    aSystemupdate// "SystemUpdate"
0x3d9ff  ldc.i4.s 0x1E
0x3da01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3da06  dup
0x3da07  ldstr    aUpdate// "Update"
0x3da0c  ldc.i4.s 0x1F
0x3da0e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3da13  dup
0x3da14  ldstr    aUser// "User"
0x3da19  ldc.i4.s 0x20
0x3da1b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3da20  dup
0x3da21  ldstr    aView// "View"
0x3da26  ldc.i4.s 0x21
0x3da28  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3da2d  dup
0x3da2e  ldstr    aWeb_0// "Web"
0x3da33  ldc.i4.s 0x22
0x3da35  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3da3a  volatile.
0x3da3c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b6f-1
0x3da41  volatile.
0x3da43  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000b6f-1
0x3da48  ldloc.s  5
0x3da4a  ldloca.s 6
0x3da4c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x3da51  brfalse  loc_3DD47
0x3da56  ldloc.s  6
0x3da58  switch   loc_3DAEE, loc_3DB00, loc_3DB12, loc_3DB24, loc_3DB36, loc_3DB48, loc_3DB5A, loc_3DB6C, loc_3DB7E, loc_3DB90, loc_3DBA2, loc_3DBB4, loc_3DBC6, loc_3DBD8, loc_3DBEA, loc_3DBFC, loc_3DC0E, loc_3DC20, loc_3DC32, loc_3DC44, loc_3DC56, loc_3DC68, loc_3DC7A, loc_3DC8C, loc_3DC9E, loc_3DCB0, loc_3DCC2, loc_3DCD1, loc_3DCE0, loc_3DCEF, loc_3DCFE, loc_3DD0D, loc_3DD1C, loc_3DD2B, loc_3DD3A
0x3dae9  br       loc_3DD47
0x3daee  ldloc.0
0x3daef  ldloc.1
0x3daf0  ldarg.3
0x3daf1  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3daf6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Activity(bool)
0x3dafb  br       loc_3DD47
0x3db00  ldloc.0
0x3db01  ldloc.1
0x3db02  ldarg.3
0x3db03  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3db08  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Add(bool)
0x3db0d  br       loc_3DD47
0x3db12  ldloc.0
0x3db13  ldloc.1
0x3db14  ldarg.3
0x3db15  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3db1a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Alert(bool)
0x3db1f  br       loc_3DD47
0x3db24  ldloc.0
0x3db25  ldloc.1
0x3db26  ldarg.3
0x3db27  call     T0x2B00015A
0x3db2c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ChangeTokenEnd(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x3db31  br       loc_3DD47
0x3db36  ldloc.0
0x3db37  ldloc.1
0x3db38  ldarg.3
0x3db39  call     T0x2B00015A
0x3db3e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ChangeTokenStart(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x3db43  br       loc_3DD47
0x3db48  ldloc.0
0x3db49  ldloc.1
0x3db4a  ldarg.3
0x3db4b  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3db50  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ContentType(bool)
0x3db55  br       loc_3DD47
0x3db5a  ldloc.0
0x3db5b  ldloc.1
0x3db5c  ldarg.3
0x3db5d  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3db62  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Delete(bool)
0x3db67  br       loc_3DD47
0x3db6c  ldloc.0
0x3db6d  ldloc.1
0x3db6e  ldarg.3
0x3db6f  call     int64 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt64(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3db74  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_FetchLimit(int64)
0x3db79  br       loc_3DD47
0x3db7e  ldloc.0
0x3db7f  ldloc.1
0x3db80  ldarg.3
0x3db81  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3db86  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Field(bool)
0x3db8b  br       loc_3DD47
0x3db90  ldloc.0
0x3db91  ldloc.1
0x3db92  ldarg.3
0x3db93  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3db98  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_File(bool)
0x3db9d  br       loc_3DD47
0x3dba2  ldloc.0
0x3dba3  ldloc.1
0x3dba4  ldarg.3
0x3dba5  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dbaa  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Folder(bool)
0x3dbaf  br       loc_3DD47
0x3dbb4  ldloc.0
0x3dbb5  ldloc.1
0x3dbb6  ldarg.3
0x3dbb7  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dbbc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Group(bool)
0x3dbc1  br       loc_3DD47
0x3dbc6  ldloc.0
0x3dbc7  ldloc.1
0x3dbc8  ldarg.3
0x3dbc9  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dbce  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_GroupMembershipAdd(bool)
0x3dbd3  br       loc_3DD47
0x3dbd8  ldloc.0
0x3dbd9  ldloc.1
0x3dbda  ldarg.3
0x3dbdb  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dbe0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_GroupMembershipDelete(bool)
0x3dbe5  br       loc_3DD47
0x3dbea  ldloc.0
0x3dbeb  ldloc.1
0x3dbec  ldarg.3
0x3dbed  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dbf2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Item(bool)
0x3dbf7  br       loc_3DD47
0x3dbfc  ldloc.0
0x3dbfd  ldloc.1
0x3dbfe  ldarg.3
0x3dbff  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dc04  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_LatestFirst(bool)
0x3dc09  br       loc_3DD47
0x3dc0e  ldloc.0
0x3dc0f  ldloc.1
0x3dc10  ldarg.3
0x3dc11  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dc16  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_List(bool)
0x3dc1b  br       loc_3DD47
0x3dc20  ldloc.0
0x3dc21  ldloc.1
0x3dc22  ldarg.3
0x3dc23  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3dc28  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Move(bool)
0x3dc2d  br       loc_3DD47
0x3dc32  ldloc.0
0x3dc33  ldloc.1
0x3dc34  ldarg.3
  ... truncated ...
```
