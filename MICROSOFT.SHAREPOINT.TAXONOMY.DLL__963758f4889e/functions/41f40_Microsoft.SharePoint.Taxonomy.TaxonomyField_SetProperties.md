# Microsoft.SharePoint.Taxonomy.TaxonomyField::SetProperties

- ea: `0x41f40`
- end: `0x420f2`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyField::SetProperties`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x41c70`

## callees

- `0x41420`
- `0x41530`
- `0x41580`
- `0x415d0`
- `0x41610`
- `0x41660`
- `0x41790`
- `0x417d0`
- `0x41810`
- `0x41c30`
- `0x41ef0`
- `0x41f40`

## string_xrefs

- `0x42014`: `UserCreated`
- `0x42099`: `IsPathRendered`
- `0x420cf`: `CreateValuesInEditForm`
- `0x420b4`: `TargetTemplate`
- `0x41f94`: `Could not create the taxonomy field.  Field name is {0}, URL is {1}`

## pseudocode

```c

```

## disassembly

```asm
0x41f40  ldarg.0
0x41f41  ldstr    aSspid_0// "SspId"
0x41f46  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x41f4b  stloc.0
0x41f4c  ldloc.0
0x41f4d  brfalse.s loc_41F5B
0x41f4f  ldarg.0
0x41f50  ldloc.0
0x41f51  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::ParseGuidFromCustomProperty(object obj)
0x41f56  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_SspId(valuetype [mscorlib]System.Guid value)
0x41f5b  ldarg.0
0x41f5c  ldstr    aTermsetid// "TermSetId"
0x41f61  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x41f66  stloc.0
0x41f67  ldloc.0
0x41f68  brfalse.s loc_41FDD
0x41f6a  ldloc.0
0x41f6b  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::ParseGuidFromCustomProperty(object obj)
0x41f70  stloc.1
0x41f71  ldloc.1
0x41f72  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x41f77  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x41f7c  brfalse.s loc_41FDD
0x41f7e  ldarg.0
0x41f7f  ldloc.1
0x41f80  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_TermSetId(valuetype [mscorlib]System.Guid value)
0x41f85  leave.s  loc_41FDD
0x41f87  pop
0x41f88  ldc.i4   0x31787862
0x41f8d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x41f92  ldc.i4.s 0xA
0x41f94  ldstr    aCouldNotCreate// "Could not create the taxonomy field.  F"...
0x41f99  ldc.i4.2
0x41f9a  newarr   [mscorlib]System.Object
0x41f9f  stloc.2
0x41fa0  ldloc.2
0x41fa1  ldc.i4.0
0x41fa2  ldarg.0
0x41fa3  call     instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Title()
0x41fa8  stelem.ref
0x41fa9  ldloc.2
0x41faa  ldc.i4.1
0x41fab  ldarg.0
0x41fac  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldsCollection
0x41fb1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection::get_List()
0x41fb6  brtrue.s loc_41FBF
0x41fb8  ldstr    aUnknownList// "unknown list"
0x41fbd  br.s     loc_41FD4
0x41fbf  ldarg.0
0x41fc0  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldsCollection
0x41fc5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection::get_List()
0x41fca  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_DefaultViewPath()
0x41fcf  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath::get_DecodedUrl()
0x41fd4  stelem.ref
0x41fd5  ldloc.2
0x41fd6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x41fdb  leave.s  loc_41FDD
0x41fdd  ldarg.0
0x41fde  ldstr    aIskeyword// "IsKeyword"
0x41fe3  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x41fe8  stloc.0
0x41fe9  ldloc.0
0x41fea  brfalse.s loc_41FF8
0x41fec  ldarg.0
0x41fed  ldloc.0
0x41fee  unbox.any [mscorlib]System.Boolean
0x41ff3  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_IsKeyword(bool value)
0x41ff8  ldarg.0
0x41ff9  ldstr    aAnchorid// "AnchorId"
0x41ffe  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x42003  stloc.0
0x42004  ldloc.0
0x42005  brfalse.s loc_42013
0x42007  ldarg.0
0x42008  ldloc.0
0x42009  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::ParseGuidFromCustomProperty(object obj)
0x4200e  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_AnchorId(valuetype [mscorlib]System.Guid value)
0x42013  ldarg.0
0x42014  ldstr    aUsercreated// "UserCreated"
0x42019  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x4201e  stloc.0
0x4201f  ldloc.0
0x42020  brfalse.s loc_4202E
0x42022  ldarg.0
0x42023  ldloc.0
0x42024  unbox.any [mscorlib]System.Boolean
0x42029  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_UserCreated(bool value)
0x4202e  ldarg.0
0x4202f  ldstr    aOpen// "Open"
0x42034  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x42039  stloc.0
0x4203a  ldloc.0
0x4203b  brfalse.s loc_42049
0x4203d  ldarg.0
0x4203e  ldloc.0
0x4203f  unbox.any [mscorlib]System.Boolean
0x42044  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_Open(bool value)
0x42049  ldarg.0
0x4204a  ldstr    aTextfield// "TextField"
0x4204f  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x42054  stloc.0
0x42055  ldloc.0
0x42056  brfalse.s loc_42098
0x42058  ldarg.0
0x42059  ldloc.0
0x4205a  castclass [mscorlib]System.String
0x4205f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x42064  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_TextField(valuetype [mscorlib]System.Guid value)
0x42069  leave.s  loc_42098
0x4206b  pop
0x4206c  ldarg.0
0x4206d  call     instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Id()
0x42072  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::HashTagsFieldGuid
0x42077  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4207c  brfalse.s loc_4208B
0x4207e  ldarg.0
0x4207f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::HashTagsHTFieldId
0x42084  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::textField
0x42089  br.s     loc_42096
0x4208b  ldarg.0
0x4208c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x42091  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::textField
0x42096  leave.s  loc_42098
0x42098  ldarg.0
0x42099  ldstr    aIspathrendered// "IsPathRendered"
0x4209e  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x420a3  stloc.0
0x420a4  ldloc.0
0x420a5  brfalse.s loc_420B3
0x420a7  ldarg.0
0x420a8  ldloc.0
0x420a9  unbox.any [mscorlib]System.Boolean
0x420ae  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_IsPathRendered(bool value)
0x420b3  ldarg.0
0x420b4  ldstr    aTargettemplate// "TargetTemplate"
0x420b9  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x420be  stloc.0
0x420bf  ldloc.0
0x420c0  brfalse.s loc_420CE
0x420c2  ldarg.0
0x420c3  ldloc.0
0x420c4  castclass [mscorlib]System.String
0x420c9  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_TargetTemplate(string value)
0x420ce  ldarg.0
0x420cf  ldstr    aCreatevaluesin// "CreateValuesInEditForm"
0x420d4  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x420d9  stloc.0
0x420da  ldloc.0
0x420db  brfalse.s loc_420EA
0x420dd  ldarg.0
0x420de  ldloc.0
0x420df  unbox.any [mscorlib]System.Boolean
0x420e4  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_CreateValuesInEditForm(bool value)
0x420e9  ret
0x420ea  ldarg.0
0x420eb  ldc.i4.0
0x420ec  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_CreateValuesInEditForm(bool value)
0x420f1  ret
```
