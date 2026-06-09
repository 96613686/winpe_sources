# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::UpdateSiteHiddenList

- ea: `0x484e0`
- end: `0x48624`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::UpdateSiteHiddenList`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x47a50`

## callees

- `0x47fc0`
- `0x48160`
- `0x484e0`

## string_xrefs

- `0x485ea`: `Trying to update a site but the hidden list is null`
- `0x48600`: `Hidden list is finished being updated for a site ID {0}`

## pseudocode

```c

```

## disassembly

```asm
0x484e0  ldarg.1
0x484e1  brfalse  loc_485DE
0x484e6  ldarg.2
0x484e7  brfalse  loc_485DE
0x484ec  ldarg.0
0x484ed  ldarg.s  4
0x484ef  stfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x484f4  ldarg.0
0x484f5  ldc.i4.s 0x64
0x484f7  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x484fc  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem[] Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::batchTermSetItems
0x48501  ldarg.0
0x48502  ldc.i4.s 0x64
0x48504  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x48509  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem[] Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::batchKeywordItems
0x4850e  ldarg.0
0x4850f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x48514  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termSetGuids
0x48519  ldarg.0
0x4851a  ldc.i4.s 0x64
0x4851c  newarr   [mscorlib]System.Guid
0x48521  stfld    valuetype [mscorlib]System.Guid[] Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::keywordGuids
0x48526  ldarg.0
0x48527  ldc.i4.0
0x48528  stfld    int32 Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termSetIndex
0x4852d  ldarg.0
0x4852e  ldc.i4.0
0x4852f  stfld    int32 Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::keywordIndex
0x48534  ldarg.0
0x48535  ldftn    instance void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::ProcessItems(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem currentItem)
0x4853b  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator/ItemProcessor::.ctor(object, native int)
0x48540  stloc.0
0x48541  ldnull
0x48542  ldftn    bool Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::ProcessItemsError(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem item, class [mscorlib]System.Exception err)
0x48548  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator/ItemProcessorErrorCallout::.ctor(object, native int)
0x4854d  stloc.1
0x4854e  ldarg.3
0x4854f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x48554  brfalse.s loc_48567
0x48556  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator::.ctor()
0x4855b  stloc.2
0x4855c  ldloc.2
0x4855d  ldarg.2
0x4855e  ldloc.0
0x4855f  ldloc.1
0x48560  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator::ProcessListItems(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList, class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator/ItemProcessor, class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator/ItemProcessorErrorCallout)
0x48565  br.s     loc_48586
0x48567  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPQuery::.ctor()
0x4856c  stloc.3
0x4856d  ldloc.3
0x4856e  ldarg.3
0x4856f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPQuery::set_ViewXml(string)
0x48574  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator::.ctor()
0x48579  stloc.s  4
0x4857b  ldloc.s  4
0x4857d  ldarg.2
0x4857e  ldloc.3
0x4857f  ldloc.0
0x48580  ldloc.1
0x48581  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator::ProcessListItems(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList, class [Microsoft.SharePoint]Microsoft.SharePoint.SPQuery, class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator/ItemProcessor, class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ContentIterator/ItemProcessorErrorCallout)
0x48586  ldarg.0
0x48587  ldfld    int32 Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::keywordIndex
0x4858c  brfalse.s loc_485B1
0x4858e  ldarg.0
0x4858f  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem[] Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::batchKeywordItems
0x48594  ldarg.0
0x48595  ldfld    valuetype [mscorlib]System.Guid[] Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::keywordGuids
0x4859a  ldarg.0
0x4859b  ldfld    int32 Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::keywordIndex
0x485a0  ldarg.0
0x485a1  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x485a6  ldarg.0
0x485a7  ldflda   class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::listItemIdsForCatalogPush
0x485ac  call     void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::BatchUpdateKeywordItems(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem[] items, valuetype [mscorlib]System.Guid[] keywordGuids, int32 size, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class [mscorlib]System.Collections.Generic.List`1<int32>& listItemIdsForCatalogPush)
0x485b1  ldarg.0
0x485b2  ldfld    int32 Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termSetIndex
0x485b7  brfalse.s loc_485F4
0x485b9  ldarg.0
0x485ba  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem[] Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::batchTermSetItems
0x485bf  ldarg.0
0x485c0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termSetGuids
0x485c5  ldarg.0
0x485c6  ldfld    int32 Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termSetIndex
0x485cb  ldarg.0
0x485cc  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x485d1  ldarg.0
0x485d2  ldflda   class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::listItemIdsForCatalogPush
0x485d7  call     void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::BatchUpdateBoundTermSetItems(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem[] items, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> termSetGuids, int32 size, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class [mscorlib]System.Collections.Generic.List`1<int32>& listItemIdsForCatalogPush)
0x485dc  br.s     loc_485F4
0x485de  ldc.i4   0x656E3039
0x485e3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x485e8  ldc.i4.s 0xA
0x485ea  ldstr    aTryingToUpdate// "Trying to update a site but the hidden "...
0x485ef  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x485f4  ldc.i4   0x656E3061
0x485f9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x485fe  ldc.i4.s 0x32
0x48600  ldstr    aHiddenListIsFi// "Hidden list is finished being updated f"...
0x48605  ldc.i4.1
0x48606  newarr   [mscorlib]System.Object
0x4860b  stloc.s  5
0x4860d  ldloc.s  5
0x4860f  ldc.i4.0
0x48610  ldarg.1
0x48611  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x48616  box      [mscorlib]System.Guid
0x4861b  stelem.ref
0x4861c  ldloc.s  5
0x4861e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x48623  ret
```
