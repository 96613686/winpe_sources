# Microsoft.SharePoint.Administration.SPContentServiceAppPermissionProvider::get_PermissionAliasMap

- ea: `0x282b20`
- end: `0x282bec`
- name: `Microsoft.SharePoint.Administration.SPContentServiceAppPermissionProvider::get_PermissionAliasMap`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x282bf0`

## callees

- `0x282b20`

## string_xrefs

- `0x282b31`: `files.read`
- `0x282b36`: `myfiles.read`
- `0x282b41`: `files.readwrite`
- `0x282b46`: `myfiles.write`
- `0x282b51`: `files.read.all`
- `0x282b56`: `allfiles.read`
- `0x282b61`: `files.readwrite.all`
- `0x282b66`: `allfiles.write`
- `0x282b71`: `sites.read.all`
- `0x282b76`: `allsites.read`
- `0x282bd6`: `allsites.read`
- `0x282b81`: `sites.readwrite.all`
- `0x282b86`: `allsites.write`
- `0x282bb1`: `group.read.all`
- `0x282bb6`: `group.read`
- `0x282bc1`: `group.readwrite.all`
- `0x282bc6`: `group.write`
- `0x282bd1`: `accessrequest.approval`

## pseudocode

```c

```

## disassembly

```asm
0x282b20  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Administration.SPContentServiceAppPermissionProvider::permissionMap
0x282b25  brtrue   loc_282BE6
0x282b2a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x282b2f  stloc.0
0x282b30  ldloc.0
0x282b31  ldstr    aFilesRead// "files.read"
0x282b36  ldstr    aMyfilesRead// "myfiles.read"
0x282b3b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282b40  ldloc.0
0x282b41  ldstr    aFilesReadwrite// "files.readwrite"
0x282b46  ldstr    aMyfilesWrite// "myfiles.write"
0x282b4b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282b50  ldloc.0
0x282b51  ldstr    aFilesReadAll// "files.read.all"
0x282b56  ldstr    aAllfilesRead// "allfiles.read"
0x282b5b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282b60  ldloc.0
0x282b61  ldstr    aFilesReadwrite_0// "files.readwrite.all"
0x282b66  ldstr    aAllfilesWrite// "allfiles.write"
0x282b6b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282b70  ldloc.0
0x282b71  ldstr    aSitesReadAll// "sites.read.all"
0x282b76  ldstr    aAllsitesRead// "allsites.read"
0x282b7b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282b80  ldloc.0
0x282b81  ldstr    aSitesReadwrite// "sites.readwrite.all"
0x282b86  ldstr    aAllsitesWrite// "allsites.write"
0x282b8b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282b90  ldloc.0
0x282b91  ldstr    aSitesManageAll// "sites.manage.all"
0x282b96  ldstr    aAllsitesManage// "allsites.manage"
0x282b9b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282ba0  ldloc.0
0x282ba1  ldstr    aSitesFullcontr// "sites.fullcontrol.all"
0x282ba6  ldstr    aAllsitesFullco// "allsites.fullcontrol"
0x282bab  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282bb0  ldloc.0
0x282bb1  ldstr    aGroupReadAll// "group.read.all"
0x282bb6  ldstr    aGroupRead// "group.read"
0x282bbb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282bc0  ldloc.0
0x282bc1  ldstr    aGroupReadwrite// "group.readwrite.all"
0x282bc6  ldstr    aGroupWrite// "group.write"
0x282bcb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282bd0  ldloc.0
0x282bd1  ldstr    aAccessrequestA// "accessrequest.approval"
0x282bd6  ldstr    aAllsitesRead// "allsites.read"
0x282bdb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x282be0  ldloc.0
0x282be1  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Administration.SPContentServiceAppPermissionProvider::permissionMap
0x282be6  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Administration.SPContentServiceAppPermissionProvider::permissionMap
0x282beb  ret
```
