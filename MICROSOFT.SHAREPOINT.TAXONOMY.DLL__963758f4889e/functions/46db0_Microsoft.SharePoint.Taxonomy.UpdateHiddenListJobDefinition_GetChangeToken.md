# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetChangeToken

- ea: `0x46db0`
- end: `0x46e3e`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetChangeToken`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x46f90`

## callees

- `0x2ac20`
- `0x46db0`

## string_xrefs

- `0x46e00`: `TimeOfLastTaxonomyUpdate`
- `0x46dca`: `TAX_TimeOfLastTaxonomyUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x46db0  ldnull
0x46db1  stloc.0
0x46db2  ldarg.0
0x46db3  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46db8  ldnull
0x46db9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x46dbe  brfalse.s loc_46E3C
0x46dc0  ldarg.1
0x46dc1  ldnull
0x46dc2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x46dc7  brfalse.s loc_46E3C
0x46dc9  ldarg.1
0x46dca  ldstr    aTaxTimeoflastt// "TAX_TimeOfLastTaxonomyUpdate"
0x46dcf  ldarga.s 2
0x46dd1  constrained. [mscorlib]System.Guid
0x46dd7  callvirt instance string [mscorlib]System.Object::ToString()
0x46ddc  call     string [mscorlib]System.String::Concat(string, string)
0x46de1  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobStateManager::ReadToken(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, string)
0x46de6  stloc.1
0x46de7  ldloc.1
0x46de8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46ded  brfalse.s loc_46E2D
0x46def  ldarg.0
0x46df0  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46df5  ldarg.1
0x46df6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x46dfb  box      [mscorlib]System.Guid
0x46e00  ldstr    aTimeoflasttaxo// "TimeOfLastTaxonomyUpdate"
0x46e05  ldarga.s 2
0x46e07  constrained. [mscorlib]System.Guid
0x46e0d  callvirt instance string [mscorlib]System.Object::ToString()
0x46e12  call     string [mscorlib]System.String::Concat(object, object, object)
0x46e17  callvirt T0x2B000064
0x46e1c  stloc.2
0x46e1d  ldloc.2
0x46e1e  ldnull
0x46e1f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x46e24  brfalse.s loc_46E2D
0x46e26  ldloc.2
0x46e27  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.PersistedChangeToken::get_ChangeToken()
0x46e2c  stloc.1
0x46e2d  ldloc.1
0x46e2e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46e33  brtrue.s loc_46E3C
0x46e35  ldloc.1
0x46e36  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken::.ctor(string)
0x46e3b  stloc.0
0x46e3c  ldloc.0
0x46e3d  ret
```
