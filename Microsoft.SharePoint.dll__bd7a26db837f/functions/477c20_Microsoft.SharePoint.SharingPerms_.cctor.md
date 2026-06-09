# Microsoft.SharePoint.SharingPerms::.cctor

- ea: `0x477c20`
- end: `0x478081`
- name: `Microsoft.SharePoint.SharingPerms::.cctor`
- size: `1121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4780a0`

## string_xrefs

- `0x477da3`: `perms_STR_UPDATE_PERSONAL_WEBPARTS_DISPLAY`
- `0x477da8`: `perms_STR_UPDATE_PERSONAL_WEBPARTS_DESCRIPTION`
- `0x477dfd`: `perms_STR_DELETE_ITEMS_DISPLAY`
- `0x477e02`: `perms_STR_DELETE_ITEMS_DESCRIPTION`
- `0x477e81`: `perms_STR_CREATE_A_SITE_DISPLAY`
- `0x477e86`: `perms_STR_CREATE_A_SITE_DESCRIPTION`
- `0x477f06`: `perms_STR_OPENITEMS_DISPLAY`
- `0x477f0b`: `perms_STR_OPENITEMS_DESCRIPTION`
- `0x477f47`: `perms_STR_DELETEVERSIONS_DISPLAY`
- `0x477f4c`: `perms_STR_DELETEVERSIONS_DESCRIPTION`
- `0x477f8e`: `perms_STR_CREATEALERTS_DISPLAY`
- `0x477f93`: `perms_STR_CREATEALERTS_DESCRIPTION`
- `0x478041`: `perms_STR_OPENWEB_DISPLAY`
- `0x478046`: `perms_STR_OPENWEB_DESCRIPTION`

## pseudocode

```c

```

## disassembly

```asm
0x477c20  ldc.i4.s 0x21
0x477c22  newarr   PermNameDescMap
0x477c27  stloc.0
0x477c28  ldloc.0
0x477c29  ldc.i4.0
0x477c2a  ldelema  PermNameDescMap
0x477c2f  ldc.i4   0x2000000
0x477c34  conv.i8
0x477c35  ldstr    aPermsStrManage// "perms_STR_MANAGE_PERMISSIONS_DISPLAY"
0x477c3a  ldstr    aPermsStrManage_0// "perms_STR_MANAGE_PERMISSIONS_DESCRIPTIO"...
0x477c3f  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477c44  stobj    PermNameDescMap
0x477c49  ldloc.0
0x477c4a  ldc.i4.1
0x477c4b  ldelema  PermNameDescMap
0x477c50  ldc.i4   0x200000
0x477c55  conv.i8
0x477c56  ldstr    aPermsStrViewUs// "perms_STR_VIEW_USAGE_DATA_DISPLAY"
0x477c5b  ldstr    aPermsStrViewUs_0// "perms_STR_VIEW_USAGE_DATA_DESCRIPTION"
0x477c60  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477c65  stobj    PermNameDescMap
0x477c6a  ldloc.0
0x477c6b  ldc.i4.2
0x477c6c  ldelema  PermNameDescMap
0x477c71  ldc.i4   0x800000
0x477c76  conv.i8
0x477c77  ldstr    aPermsStrManage_1// "perms_STR_MANAGE_SUBWEBS_DISPLAY"
0x477c7c  ldstr    aPermsStrManage_2// "perms_STR_MANAGE_SUBWEBS_DESCRIPTION"
0x477c81  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477c86  stobj    PermNameDescMap
0x477c8b  ldloc.0
0x477c8c  ldc.i4.3
0x477c8d  ldelema  PermNameDescMap
0x477c92  ldc.i4   0x40000000
0x477c97  conv.i8
0x477c98  ldstr    aPermsStrManage_3// "perms_STR_MANAGE_WEB_DISPLAY"
0x477c9d  ldstr    aPermsStrManage_4// "perms_STR_MANAGE_WEB_DESCRIPTION"
0x477ca2  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477ca7  stobj    PermNameDescMap
0x477cac  ldloc.0
0x477cad  ldc.i4.4
0x477cae  ldelema  PermNameDescMap
0x477cb3  ldc.i4   0x40000
0x477cb8  conv.i8
0x477cb9  ldstr    aPermsStrAddAnd// "perms_STR_ADD_AND_CUSTOMIZE_PAGES_DISPL"...
0x477cbe  ldstr    aPermsStrAddAnd_0// "perms_STR_ADD_AND_CUSTOMIZE_PAGES_DESCR"...
0x477cc3  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477cc8  stobj    PermNameDescMap
0x477ccd  ldloc.0
0x477cce  ldc.i4.5
0x477ccf  ldelema  PermNameDescMap
0x477cd4  ldc.i4   0x800
0x477cd9  conv.i8
0x477cda  ldstr    aPermsStrManage_5// "perms_STR_MANAGE_LISTS_DISPLAY"
0x477cdf  ldstr    aPermsStrManage_6// "perms_STR_MANAGE_LISTS_DESCRIPTION"
0x477ce4  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477ce9  stobj    PermNameDescMap
0x477cee  ldloc.0
0x477cef  ldc.i4.6
0x477cf0  ldelema  PermNameDescMap
0x477cf5  ldc.i4   0x80000
0x477cfa  conv.i8
0x477cfb  ldstr    aPermsStrApplyT// "perms_STR_APPLY_THEMES_AND_BORDERS_DISP"...
0x477d00  ldstr    aPermsStrApplyT_0// "perms_STR_APPLY_THEMES_AND_BORDERS_DESC"...
0x477d05  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477d0a  stobj    PermNameDescMap
0x477d0f  ldloc.0
0x477d10  ldc.i4.7
0x477d11  ldelema  PermNameDescMap
0x477d16  ldc.i4   0x100000
0x477d1b  conv.i8
0x477d1c  ldstr    aPermsStrApplyS// "perms_STR_APPLY_STYLE_SHEETS_DISPLAY"
0x477d21  ldstr    aPermsStrApplyS_0// "perms_STR_APPLY_STYLE_SHEETS_DESCRIPTIO"...
0x477d26  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477d2b  stobj    PermNameDescMap
0x477d30  ldloc.0
0x477d31  ldc.i4.8
0x477d32  ldelema  PermNameDescMap
0x477d37  ldc.i4   0x100
0x477d3c  conv.i8
0x477d3d  ldstr    aPermsStrCancel// "perms_STR_CANCEL_CHECK_OUT_DISPLAY"
0x477d42  ldstr    aPermsStrCancel_0// "perms_STR_CANCEL_CHECK_OUT_DESCRIPTION"
0x477d47  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477d4c  stobj    PermNameDescMap
0x477d51  ldloc.0
0x477d52  ldc.i4.s 9
0x477d54  ldelema  PermNameDescMap
0x477d59  ldc.i4   0x200
0x477d5e  conv.i8
0x477d5f  ldstr    aPermsStrManage_7// "perms_STR_MANAGE_PERSONAL_VIEWS_DISPLAY"
0x477d64  ldstr    aPermsStrManage_8// "perms_STR_MANAGE_PERSONAL_VIEWS_DESCRIP"...
0x477d69  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477d6e  stobj    PermNameDescMap
0x477d73  ldloc.0
0x477d74  ldc.i4.s 0xA
0x477d76  ldelema  PermNameDescMap
0x477d7b  ldc.i4   0x10000000
0x477d80  conv.i8
0x477d81  ldstr    aPermsStrAddRem// "perms_STR_ADD_REM_PRIVATE_WEBPARTS_DISP"...
0x477d86  ldstr    aPermsStrAddRem_0// "perms_STR_ADD_REM_PRIVATE_WEBPARTS_DESC"...
0x477d8b  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477d90  stobj    PermNameDescMap
0x477d95  ldloc.0
0x477d96  ldc.i4.s 0xB
0x477d98  ldelema  PermNameDescMap
0x477d9d  ldc.i4   0x20000000
0x477da2  conv.i8
0x477da3  ldstr    aPermsStrUpdate// "perms_STR_UPDATE_PERSONAL_WEBPARTS_DISP"...
0x477da8  ldstr    aPermsStrUpdate_0// "perms_STR_UPDATE_PERSONAL_WEBPARTS_DESC"...
0x477dad  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477db2  stobj    PermNameDescMap
0x477db7  ldloc.0
0x477db8  ldc.i4.s 0xC
0x477dba  ldelema  PermNameDescMap
0x477dbf  ldc.i4.2
0x477dc0  conv.i8
0x477dc1  ldstr    aPermsStrAddIte// "perms_STR_ADD_ITEMS_DISPLAY"
0x477dc6  ldstr    aPermsStrAddIte_0// "perms_STR_ADD_ITEMS_DESCRIPTION"
0x477dcb  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477dd0  stobj    PermNameDescMap
0x477dd5  ldloc.0
0x477dd6  ldc.i4.s 0xD
0x477dd8  ldelema  PermNameDescMap
0x477ddd  ldc.i4.4
0x477dde  conv.i8
0x477ddf  ldstr    aPermsStrEditIt// "perms_STR_EDIT_ITEMS_DISPLAY"
0x477de4  ldstr    aPermsStrEditIt_0// "perms_STR_EDIT_ITEMS_DESCRIPTION"
0x477de9  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477dee  stobj    PermNameDescMap
0x477df3  ldloc.0
0x477df4  ldc.i4.s 0xE
0x477df6  ldelema  PermNameDescMap
0x477dfb  ldc.i4.8
0x477dfc  conv.i8
0x477dfd  ldstr    aPermsStrDelete// "perms_STR_DELETE_ITEMS_DISPLAY"
0x477e02  ldstr    aPermsStrDelete_0// "perms_STR_DELETE_ITEMS_DESCRIPTION"
0x477e07  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477e0c  stobj    PermNameDescMap
0x477e11  ldloc.0
0x477e12  ldc.i4.s 0xF
0x477e14  ldelema  PermNameDescMap
0x477e19  ldc.i4   0x1000000
0x477e1e  conv.i8
0x477e1f  ldstr    aPermsStrManage_9// "perms_STR_MANAGE_GROUPS_DISPLAY"
0x477e24  ldstr    aPermsStrManage_10// "perms_STR_MANAGE_GROUPS_DESCRIPTION"
0x477e29  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477e2e  stobj    PermNameDescMap
0x477e33  ldloc.0
0x477e34  ldc.i4.s 0x10
0x477e36  ldelema  PermNameDescMap
0x477e3b  ldc.i4   0x4000000
0x477e40  conv.i8
0x477e41  ldstr    aPermsStrBrowse// "perms_STR_BROWSE_DIRECTORIES_DISPLAY"
0x477e46  ldstr    aPermsStrBrowse_0// "perms_STR_BROWSE_DIRECTORIES_DESCRIPTIO"...
0x477e4b  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477e50  stobj    PermNameDescMap
0x477e55  ldloc.0
0x477e56  ldc.i4.s 0x11
0x477e58  ldelema  PermNameDescMap
0x477e5d  ldc.i4.1
0x477e5e  conv.i8
0x477e5f  ldstr    aPermsStrViewIt// "perms_STR_VIEW_ITEMS_DISPLAY"
0x477e64  ldstr    aPermsStrViewIt_0// "perms_STR_VIEW_ITEMS_DESCRIPTION"
0x477e69  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477e6e  stobj    PermNameDescMap
0x477e73  ldloc.0
0x477e74  ldc.i4.s 0x12
0x477e76  ldelema  PermNameDescMap
0x477e7b  ldc.i4   0x400000
0x477e80  conv.i8
0x477e81  ldstr    aPermsStrCreate// "perms_STR_CREATE_A_SITE_DISPLAY"
0x477e86  ldstr    aPermsStrCreate_0// "perms_STR_CREATE_A_SITE_DESCRIPTION"
0x477e8b  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477e90  stobj    PermNameDescMap
0x477e95  ldloc.0
0x477e96  ldc.i4.s 0x13
0x477e98  ldelema  PermNameDescMap
0x477e9d  ldc.i4   0x20000
0x477ea2  conv.i8
0x477ea3  ldstr    aPermsStrViewPa// "perms_STR_VIEW_PAGES_DISPLAY"
0x477ea8  ldstr    aPermsStrViewPa_0// "perms_STR_VIEW_PAGES_DESCRIPTION"
0x477ead  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477eb2  stobj    PermNameDescMap
0x477eb7  ldloc.0
0x477eb8  ldc.i4.s 0x14
0x477eba  ldelema  PermNameDescMap
0x477ebf  ldc.i4.s 0x10
0x477ec1  conv.i8
0x477ec2  ldstr    aPermsStrApprov// "perms_STR_APPROVE_ITEMS_DISPLAY"
0x477ec7  ldstr    aPermsStrApprov_0// "perms_STR_APPROVE_ITEMS_DESCRIPTION"
0x477ecc  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477ed1  stobj    PermNameDescMap
0x477ed6  ldloc.0
0x477ed7  ldc.i4.s 0x15
0x477ed9  ldelema  PermNameDescMap
0x477ede  ldc.i8   0x4000000000000000
0x477ee7  ldstr    aPermsStrEnumer// "perms_STR_ENUMERATE_PERMISSIONS_DISPLAY"
0x477eec  ldstr    aPermsStrEnumer_0// "perms_STR_ENUMERATE_PERMISSIONS_DESCRIP"...
0x477ef1  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477ef6  stobj    PermNameDescMap
0x477efb  ldloc.0
0x477efc  ldc.i4.s 0x16
0x477efe  ldelema  PermNameDescMap
0x477f03  ldc.i4.s 0x20
0x477f05  conv.i8
0x477f06  ldstr    aPermsStrOpenit// "perms_STR_OPENITEMS_DISPLAY"
0x477f0b  ldstr    aPermsStrOpenit_0// "perms_STR_OPENITEMS_DESCRIPTION"
0x477f10  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477f15  stobj    PermNameDescMap
0x477f1a  ldloc.0
0x477f1b  ldc.i4.s 0x17
0x477f1d  ldelema  PermNameDescMap
0x477f22  ldc.i4.s 0x40
0x477f24  conv.i8
0x477f25  ldstr    aPermsStrViewve// "perms_STR_VIEWVERSIONS_DISPLAY"
0x477f2a  ldstr    aPermsStrViewve_0// "perms_STR_VIEWVERSIONS_DESCRIPTION"
0x477f2f  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477f34  stobj    PermNameDescMap
0x477f39  ldloc.0
0x477f3a  ldc.i4.s 0x18
0x477f3c  ldelema  PermNameDescMap
0x477f41  ldc.i4   0x80
0x477f46  conv.i8
0x477f47  ldstr    aPermsStrDelete_1// "perms_STR_DELETEVERSIONS_DISPLAY"
0x477f4c  ldstr    aPermsStrDelete_2// "perms_STR_DELETEVERSIONS_DESCRIPTION"
0x477f51  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477f56  stobj    PermNameDescMap
0x477f5b  ldloc.0
0x477f5c  ldc.i4.s 0x19
0x477f5e  ldelema  PermNameDescMap
0x477f63  ldc.i4   0x8000000
0x477f68  conv.i8
0x477f69  ldstr    aPermsStrBrowse_1// "perms_STR_BROWSEUSERINFO_DISPLAY"
0x477f6e  ldstr    aPermsStrBrowse_2// "perms_STR_BROWSEUSERINFO_DESCRIPTION"
0x477f73  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477f78  stobj    PermNameDescMap
0x477f7d  ldloc.0
0x477f7e  ldc.i4.s 0x1A
0x477f80  ldelema  PermNameDescMap
0x477f85  ldc.i8   0x8000000000
0x477f8e  ldstr    aPermsStrCreate_1// "perms_STR_CREATEALERTS_DISPLAY"
0x477f93  ldstr    aPermsStrCreate_2// "perms_STR_CREATEALERTS_DESCRIPTION"
0x477f98  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477f9d  stobj    PermNameDescMap
0x477fa2  ldloc.0
0x477fa3  ldc.i4.s 0x1B
0x477fa5  ldelema  PermNameDescMap
0x477faa  ldc.i8   0x4000000000
0x477fb3  ldstr    aPermsStrManage_11// "perms_STR_MANAGEALERTS_DISPLAY"
0x477fb8  ldstr    aPermsStrManage_12// "perms_STR_MANAGEALERTS_DESCRIPTION"
0x477fbd  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477fc2  stobj    PermNameDescMap
0x477fc7  ldloc.0
0x477fc8  ldc.i4.s 0x1C
0x477fca  ldelema  PermNameDescMap
0x477fcf  ldc.i4   0x1000
0x477fd4  conv.i8
0x477fd5  ldstr    aPermsStrViewFo// "perms_STR_VIEW_FORM_PAGES_DISPLAY"
0x477fda  ldstr    aPermsStrViewFo_0// "perms_STR_VIEW_FORM_PAGES_DESCRIPTION"
0x477fdf  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x477fe4  stobj    PermNameDescMap
0x477fe9  ldloc.0
0x477fea  ldc.i4.s 0x1D
0x477fec  ldelema  PermNameDescMap
0x477ff1  ldc.i8   0x2000000000
0x477ffa  ldstr    aPermsStrUseRem// "perms_STR_USE_REMOTEAPIS_DISPLAY"
0x477fff  ldstr    aPermsStrUseRem_0// "perms_STR_USE_REMOTEAPIS_DESCRIPTION"
0x478004  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x478009  stobj    PermNameDescMap
0x47800e  ldloc.0
0x47800f  ldc.i4.s 0x1E
0x478011  ldelema  PermNameDescMap
0x478016  ldc.i8   0x1000000000
0x47801f  ldstr    aPermsStrUseCli// "perms_STR_USE_CLIENT_INTEGRATION_DISPLA"...
0x478024  ldstr    aPermsStrUseCli_0// "perms_STR_USE_CLIENT_INTEGRATION_DESCRI"...
0x478029  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x47802e  stobj    PermNameDescMap
0x478033  ldloc.0
0x478034  ldc.i4.s 0x1F
0x478036  ldelema  PermNameDescMap
0x47803b  ldc.i4   0x10000
0x478040  conv.i8
0x478041  ldstr    aPermsStrOpenwe// "perms_STR_OPENWEB_DISPLAY"
0x478046  ldstr    aPermsStrOpenwe_0// "perms_STR_OPENWEB_DESCRIPTION"
0x47804b  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x478050  stobj    PermNameDescMap
0x478055  ldloc.0
0x478056  ldc.i4.s 0x20
0x478058  ldelema  PermNameDescMap
0x47805d  ldc.i8   0x10000000000
0x478066  ldstr    aPermsStrEditMy// "perms_STR_EDIT_MY_USERINFO_DISPLAY"
0x47806b  ldstr    aPermsStrEditMy_0// "perms_STR_EDIT_MY_USERINFO_DESCRIPTION"
0x478070  newobj   instance void PermNameDescMap::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions sptIn, string strNameRes, string strDescRes)
0x478075  stobj    PermNameDescMap
0x47807a  ldloc.0
0x47807b  stsfld   valuetype PermNameDescMap[] Microsoft.SharePoint.SharingPerms::permNameDesc
0x478080  ret
```
