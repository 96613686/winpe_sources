# Microsoft.SharePoint.ServerStub.SPListItemServerStub::.cctor

- ea: `0xb760`
- end: `0xb8b4`
- name: `Microsoft.SharePoint.ServerStub.SPListItemServerStub::.cctor`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0xb89f`: `Update`
- `0xb8a7`: `SystemUpdate`
- `0xb76a`: `CommentsDisabled`
- `0xb84b`: `CommentsDisabled`
- `0xb772`: `CommentsDisabledScope`
- `0xb853`: `CommentsDisabledScope`
- `0xb7aa`: `ServerRedirectedEmbedUri`

## pseudocode

```c

```

## disassembly

```asm
0xb760  ldc.i4.s 0xB
0xb762  newarr   [mscorlib]System.String
0xb767  stloc.0
0xb768  ldloc.0
0xb769  ldc.i4.0
0xb76a  ldstr    aCommentsdisabl// "CommentsDisabled"
0xb76f  stelem.ref
0xb770  ldloc.0
0xb771  ldc.i4.1
0xb772  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
0xb777  stelem.ref
0xb778  ldloc.0
0xb779  ldc.i4.2
0xb77a  ldstr    aDisplayname// "DisplayName"
0xb77f  stelem.ref
0xb780  ldloc.0
0xb781  ldc.i4.3
0xb782  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0xb787  stelem.ref
0xb788  ldloc.0
0xb789  ldc.i4.4
0xb78a  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0xb78f  stelem.ref
0xb790  ldloc.0
0xb791  ldc.i4.5
0xb792  ldstr    aFilesystemobje// "FileSystemObjectType"
0xb797  stelem.ref
0xb798  ldloc.0
0xb799  ldc.i4.6
0xb79a  ldstr    aIconoverlay// "IconOverlay"
0xb79f  stelem.ref
0xb7a0  ldloc.0
0xb7a1  ldc.i4.7
0xb7a2  ldstr    aId_0// "Id"
0xb7a7  stelem.ref
0xb7a8  ldloc.0
0xb7a9  ldc.i4.8
0xb7aa  ldstr    aServerredirect// "ServerRedirectedEmbedUri"
0xb7af  stelem.ref
0xb7b0  ldloc.0
0xb7b1  ldc.i4.s 9
0xb7b3  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xb7b8  stelem.ref
0xb7b9  ldloc.0
0xb7ba  ldc.i4.s 0xA
0xb7bc  ldstr    aClientTitle// "Client_Title"
0xb7c1  stelem.ref
0xb7c2  ldloc.0
0xb7c3  stsfld   string[] Microsoft.SharePoint.ServerStub.SPListItemServerStub::s_valueProperties
0xb7c8  ldc.i4.s 0xD
0xb7ca  newarr   [mscorlib]System.String
0xb7cf  stloc.1
0xb7d0  ldloc.1
0xb7d1  ldc.i4.0
0xb7d2  ldstr    aActivities// "Activities"
0xb7d7  stelem.ref
0xb7d8  ldloc.1
0xb7d9  ldc.i4.1
0xb7da  ldstr    aAttachmentfile// "AttachmentFiles"
0xb7df  stelem.ref
0xb7e0  ldloc.1
0xb7e1  ldc.i4.2
0xb7e2  ldstr    aContenttype// "ContentType"
0xb7e7  stelem.ref
0xb7e8  ldloc.1
0xb7e9  ldc.i4.3
0xb7ea  ldstr    aGetdlppolicyti// "GetDlpPolicyTip"
0xb7ef  stelem.ref
0xb7f0  ldloc.1
0xb7f1  ldc.i4.4
0xb7f2  ldstr    aFieldvaluesash// "FieldValuesAsHtml"
0xb7f7  stelem.ref
0xb7f8  ldloc.1
0xb7f9  ldc.i4.5
0xb7fa  ldstr    aFieldvaluesast// "FieldValuesAsText"
0xb7ff  stelem.ref
0xb800  ldloc.1
0xb801  ldc.i4.6
0xb802  ldstr    aFieldvaluesfor// "FieldValuesForEdit"
0xb807  stelem.ref
0xb808  ldloc.1
0xb809  ldc.i4.7
0xb80a  ldstr    aFile// "File"
0xb80f  stelem.ref
0xb810  ldloc.1
0xb811  ldc.i4.8
0xb812  ldstr    aFolder// "Folder"
0xb817  stelem.ref
0xb818  ldloc.1
0xb819  ldc.i4.s 9
0xb81b  ldstr    aLikedbyinforma// "LikedByInformation"
0xb820  stelem.ref
0xb821  ldloc.1
0xb822  ldc.i4.s 0xA
0xb824  ldstr    aParentlist// "ParentList"
0xb829  stelem.ref
0xb82a  ldloc.1
0xb82b  ldc.i4.s 0xB
0xb82d  ldstr    aProperties// "Properties"
0xb832  stelem.ref
0xb833  ldloc.1
0xb834  ldc.i4.s 0xC
0xb836  ldstr    aVersions// "Versions"
0xb83b  stelem.ref
0xb83c  ldloc.1
0xb83d  stsfld   string[] Microsoft.SharePoint.ServerStub.SPListItemServerStub::s_refProperties
0xb842  ldc.i4.7
0xb843  newarr   [mscorlib]System.String
0xb848  stloc.2
0xb849  ldloc.2
0xb84a  ldc.i4.0
0xb84b  ldstr    aCommentsdisabl// "CommentsDisabled"
0xb850  stelem.ref
0xb851  ldloc.2
0xb852  ldc.i4.1
0xb853  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
0xb858  stelem.ref
0xb859  ldloc.2
0xb85a  ldc.i4.2
0xb85b  ldstr    aDisplayname// "DisplayName"
0xb860  stelem.ref
0xb861  ldloc.2
0xb862  ldc.i4.3
0xb863  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0xb868  stelem.ref
0xb869  ldloc.2
0xb86a  ldc.i4.4
0xb86b  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0xb870  stelem.ref
0xb871  ldloc.2
0xb872  ldc.i4.5
0xb873  ldstr    aIconoverlay// "IconOverlay"
0xb878  stelem.ref
0xb879  ldloc.2
0xb87a  ldc.i4.6
0xb87b  ldstr    aClientTitle// "Client_Title"
0xb880  stelem.ref
0xb881  ldloc.2
0xb882  stsfld   string[] Microsoft.SharePoint.ServerStub.SPListItemServerStub::s_excludeFromDefaultRetrieveProperties
0xb887  ldstr    a53cc48c0177747// "{53cc48c0-1777-47b7-99ca-729390f06602}"
0xb88c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb891  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPListItemServerStub::s_targetTypeId
0xb896  ldc.i4.2
0xb897  newarr   [mscorlib]System.String
0xb89c  stloc.3
0xb89d  ldloc.3
0xb89e  ldc.i4.0
0xb89f  ldstr    aUpdate// "Update"
0xb8a4  stelem.ref
0xb8a5  ldloc.3
0xb8a6  ldc.i4.1
0xb8a7  ldstr    aSystemupdate// "SystemUpdate"
0xb8ac  stelem.ref
0xb8ad  ldloc.3
0xb8ae  stsfld   string[] Microsoft.SharePoint.ServerStub.SPListItemServerStub::s_checkVersionMethodNames
0xb8b3  ret
```
