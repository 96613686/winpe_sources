# Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::WritePropertiesAsJson

- ea: `0x3e6b0`
- end: `0x3ea0d`
- name: `Microsoft.SharePoint.ServerStub.SPChangeQueryValueTypeConverter::WritePropertiesAsJson`
- size: `861`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x3e6b0`

## string_xrefs

- `0x3e9ad`: `Update`
- `0x3e755`: `DeleteObject`
- `0x3e995`: `SystemUpdate`
- `0x3e8a5`: `Rename`
- `0x3e70d`: `ChangeTokenEnd`
- `0x3e725`: `ChangeTokenStart`
- `0x3e7fd`: `GroupMembershipDelete`
- `0x3e8bd`: `RequireSecurityTrim`
- `0x3e905`: `RoleAssignmentDelete`
- `0x3e935`: `RoleDefinitionDelete`
- `0x3e94d`: `RoleDefinitionUpdate`
- `0x3e965`: `SecurityPolicy`

## pseudocode

```c

```

## disassembly

```asm
0x3e6b0  ldarg.2
0x3e6b1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery
0x3e6b6  stloc.0
0x3e6b7  ldloc.0
0x3e6b8  brtrue.s loc_3E6BB
0x3e6ba  ret
0x3e6bb  ldarg.0
0x3e6bc  ldarg.1
0x3e6bd  ldarg.2
0x3e6be  ldarg.3
0x3e6bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e6c4  ldarg.1
0x3e6c5  ldstr    aActivity// "Activity"
0x3e6ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e6cf  ldarg.1
0x3e6d0  ldloc.0
0x3e6d1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Activity()
0x3e6d6  ldarg.3
0x3e6d7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e6dc  ldarg.1
0x3e6dd  ldstr    aAdd// "Add"
0x3e6e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e6e7  ldarg.1
0x3e6e8  ldloc.0
0x3e6e9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Add()
0x3e6ee  ldarg.3
0x3e6ef  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e6f4  ldarg.1
0x3e6f5  ldstr    aAlert// "Alert"
0x3e6fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e6ff  ldarg.1
0x3e700  ldloc.0
0x3e701  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Alert()
0x3e706  ldarg.3
0x3e707  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e70c  ldarg.1
0x3e70d  ldstr    aChangetokenend// "ChangeTokenEnd"
0x3e712  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e717  ldarg.1
0x3e718  ldloc.0
0x3e719  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_ChangeTokenEnd()
0x3e71e  ldarg.3
0x3e71f  call     T0x2B000024
0x3e724  ldarg.1
0x3e725  ldstr    aChangetokensta// "ChangeTokenStart"
0x3e72a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e72f  ldarg.1
0x3e730  ldloc.0
0x3e731  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_ChangeTokenStart()
0x3e736  ldarg.3
0x3e737  call     T0x2B000024
0x3e73c  ldarg.1
0x3e73d  ldstr    aContenttype// "ContentType"
0x3e742  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e747  ldarg.1
0x3e748  ldloc.0
0x3e749  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_ContentType()
0x3e74e  ldarg.3
0x3e74f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e754  ldarg.1
0x3e755  ldstr    aDeleteobject// "DeleteObject"
0x3e75a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e75f  ldarg.1
0x3e760  ldloc.0
0x3e761  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Delete()
0x3e766  ldarg.3
0x3e767  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e76c  ldarg.1
0x3e76d  ldstr    aFetchlimit// "FetchLimit"
0x3e772  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e777  ldarg.1
0x3e778  ldloc.0
0x3e779  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_FetchLimit()
0x3e77e  ldarg.3
0x3e77f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt64(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int64, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e784  ldarg.1
0x3e785  ldstr    aField// "Field"
0x3e78a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e78f  ldarg.1
0x3e790  ldloc.0
0x3e791  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Field()
0x3e796  ldarg.3
0x3e797  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e79c  ldarg.1
0x3e79d  ldstr    aFile// "File"
0x3e7a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e7a7  ldarg.1
0x3e7a8  ldloc.0
0x3e7a9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_File()
0x3e7ae  ldarg.3
0x3e7af  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e7b4  ldarg.1
0x3e7b5  ldstr    aFolder// "Folder"
0x3e7ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e7bf  ldarg.1
0x3e7c0  ldloc.0
0x3e7c1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Folder()
0x3e7c6  ldarg.3
0x3e7c7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e7cc  ldarg.1
0x3e7cd  ldstr    aGroup// "Group"
0x3e7d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e7d7  ldarg.1
0x3e7d8  ldloc.0
0x3e7d9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Group()
0x3e7de  ldarg.3
0x3e7df  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e7e4  ldarg.1
0x3e7e5  ldstr    aGroupmembershi// "GroupMembershipAdd"
0x3e7ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e7ef  ldarg.1
0x3e7f0  ldloc.0
0x3e7f1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_GroupMembershipAdd()
0x3e7f6  ldarg.3
0x3e7f7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e7fc  ldarg.1
0x3e7fd  ldstr    aGroupmembershi_0// "GroupMembershipDelete"
0x3e802  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e807  ldarg.1
0x3e808  ldloc.0
0x3e809  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_GroupMembershipDelete()
0x3e80e  ldarg.3
0x3e80f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e814  ldarg.1
0x3e815  ldstr    aItem_0// "Item"
0x3e81a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e81f  ldarg.1
0x3e820  ldloc.0
0x3e821  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Item()
0x3e826  ldarg.3
0x3e827  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e82c  ldarg.1
0x3e82d  ldstr    aLatestfirst// "LatestFirst"
0x3e832  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e837  ldarg.1
0x3e838  ldloc.0
0x3e839  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_LatestFirst()
0x3e83e  ldarg.3
0x3e83f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e844  ldarg.1
0x3e845  ldstr    aList// "List"
0x3e84a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e84f  ldarg.1
0x3e850  ldloc.0
0x3e851  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_List()
0x3e856  ldarg.3
0x3e857  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e85c  ldarg.1
0x3e85d  ldstr    aMove_0// "Move"
0x3e862  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e867  ldarg.1
0x3e868  ldloc.0
0x3e869  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Move()
0x3e86e  ldarg.3
0x3e86f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e874  ldarg.1
0x3e875  ldstr    aNavigation// "Navigation"
0x3e87a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e87f  ldarg.1
0x3e880  ldloc.0
0x3e881  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Navigation()
0x3e886  ldarg.3
0x3e887  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e88c  ldarg.1
0x3e88d  ldstr    aRecursiveall// "RecursiveAll"
0x3e892  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e897  ldarg.1
0x3e898  ldloc.0
0x3e899  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RecursiveAll()
0x3e89e  ldarg.3
0x3e89f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e8a4  ldarg.1
0x3e8a5  ldstr    aRename_0// "Rename"
0x3e8aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e8af  ldarg.1
0x3e8b0  ldloc.0
0x3e8b1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Rename()
0x3e8b6  ldarg.3
0x3e8b7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e8bc  ldarg.1
0x3e8bd  ldstr    aRequiresecurit// "RequireSecurityTrim"
0x3e8c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e8c7  ldarg.1
0x3e8c8  ldloc.0
0x3e8c9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RequireSecurityTrim()
0x3e8ce  ldarg.3
0x3e8cf  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e8d4  ldarg.1
0x3e8d5  ldstr    aRestore_0// "Restore"
0x3e8da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e8df  ldarg.1
0x3e8e0  ldloc.0
0x3e8e1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Restore()
0x3e8e6  ldarg.3
0x3e8e7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e8ec  ldarg.1
0x3e8ed  ldstr    aRoleassignment_0// "RoleAssignmentAdd"
0x3e8f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e8f7  ldarg.1
0x3e8f8  ldloc.0
0x3e8f9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleAssignmentAdd()
0x3e8fe  ldarg.3
0x3e8ff  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e904  ldarg.1
0x3e905  ldstr    aRoleassignment_1// "RoleAssignmentDelete"
0x3e90a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e90f  ldarg.1
0x3e910  ldloc.0
0x3e911  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleAssignmentDelete()
0x3e916  ldarg.3
0x3e917  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e91c  ldarg.1
0x3e91d  ldstr    aRoledefinition_0// "RoleDefinitionAdd"
0x3e922  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e927  ldarg.1
0x3e928  ldloc.0
0x3e929  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleDefinitionAdd()
0x3e92e  ldarg.3
0x3e92f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e934  ldarg.1
0x3e935  ldstr    aRoledefinition_1// "RoleDefinitionDelete"
0x3e93a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e93f  ldarg.1
0x3e940  ldloc.0
0x3e941  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleDefinitionDelete()
0x3e946  ldarg.3
0x3e947  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e94c  ldarg.1
0x3e94d  ldstr    aRoledefinition_2// "RoleDefinitionUpdate"
0x3e952  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e957  ldarg.1
0x3e958  ldloc.0
0x3e959  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_RoleDefinitionUpdate()
0x3e95e  ldarg.3
0x3e95f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e964  ldarg.1
0x3e965  ldstr    aSecuritypolicy// "SecurityPolicy"
0x3e96a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e96f  ldarg.1
0x3e970  ldloc.0
0x3e971  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_SecurityPolicy()
0x3e976  ldarg.3
0x3e977  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e97c  ldarg.1
0x3e97d  ldstr    aSite_0// "Site"
0x3e982  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e987  ldarg.1
0x3e988  ldloc.0
0x3e989  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Site()
0x3e98e  ldarg.3
0x3e98f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e994  ldarg.1
0x3e995  ldstr    aSystemupdate// "SystemUpdate"
0x3e99a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e99f  ldarg.1
0x3e9a0  ldloc.0
0x3e9a1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_SystemUpdate()
0x3e9a6  ldarg.3
0x3e9a7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e9ac  ldarg.1
0x3e9ad  ldstr    aUpdate// "Update"
0x3e9b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e9b7  ldarg.1
0x3e9b8  ldloc.0
0x3e9b9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Update()
0x3e9be  ldarg.3
0x3e9bf  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e9c4  ldarg.1
0x3e9c5  ldstr    aUser// "User"
0x3e9ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e9cf  ldarg.1
0x3e9d0  ldloc.0
0x3e9d1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_User()
0x3e9d6  ldarg.3
0x3e9d7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e9dc  ldarg.1
0x3e9dd  ldstr    aView// "View"
0x3e9e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e9e7  ldarg.1
0x3e9e8  ldloc.0
0x3e9e9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_View()
0x3e9ee  ldarg.3
0x3e9ef  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3e9f4  ldarg.1
0x3e9f5  ldstr    aWeb_0// "Web"
0x3e9fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3e9ff  ldarg.1
0x3ea00  ldloc.0
0x3ea01  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_Web()
0x3ea06  ldarg.3
0x3ea07  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3ea0c  ret
```
