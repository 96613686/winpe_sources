# Microsoft.SharePoint.Taxonomy.TermStore::DeleteLanguage

- ea: `0x54140`
- end: `0x54271`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::DeleteLanguage`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x63a0`
- `0x8cb0`

## callees

- `0x2acd0`
- `0x2df10`
- `0x336a0`
- `0x337a0`
- `0x338b0`
- `0x4cf50`
- `0x54140`
- `0x55e90`
- `0x56c80`
- `0x56e70`
- `0x579b0`

## string_xrefs

- `0x5414c`: `Begin: TermStore.DeleteLanguage(int)`
- `0x541a3`: `ErrorLastLanguageCannotBeDeleted`
- `0x541c1`: `ErrorDefaultLanguageCannotBeDeleted`
- `0x541f1`: `LanguageRemoved`
- `0x54266`: `End: TermStore.DeleteLanguage(int)`

## pseudocode

```c

```

## disassembly

```asm
0x54140  ldc.i4   0x3778736E
0x54145  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5414a  ldc.i4.s 0x64
0x5414c  ldstr    aBeginTermstore_2// "Begin: TermStore.DeleteLanguage(int)"
0x54151  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x54156  ldarg.0
0x54157  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x5415c  brfalse.s loc_54187
0x5415e  ldarg.0
0x5415f  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x54164  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext Microsoft.SharePoint.Taxonomy.TaxonomySession::get_Context()
0x54169  brfalse.s loc_54187
0x5416b  ldarg.0
0x5416c  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x54171  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext Microsoft.SharePoint.Taxonomy.TaxonomySession::get_Context()
0x54176  call     bool Microsoft.SharePoint.Taxonomy.Internal.Security::DoesUserHaveServiceAdminPermissions(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext context)
0x5417b  brfalse.s loc_54187
0x5417d  ldarg.0
0x5417e  ldc.i4.0
0x5417f  conv.i8
0x54180  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions)
0x54185  br.s     loc_54190
0x54187  ldarg.0
0x54188  ldc.i4.s 0x10
0x5418a  conv.i8
0x5418b  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions)
0x54190  ldarg.0
0x54191  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x54196  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_LanguageIds()
0x5419b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::get_Count()
0x541a0  ldc.i4.1
0x541a1  bgt.s    loc_541B3
0x541a3  ldstr    aErrorlastlangu// "ErrorLastLanguageCannotBeDeleted"
0x541a8  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x541ad  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x541b2  throw
0x541b3  ldarg.0
0x541b4  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x541b9  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_DefaultLanguage()
0x541be  ldarg.1
0x541bf  bne.un.s loc_541D1
0x541c1  ldstr    aErrordefaultla// "ErrorDefaultLanguageCannotBeDeleted"
0x541c6  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x541cb  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x541d0  throw
0x541d1  ldarg.0
0x541d2  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x541d7  ldarg.1
0x541d8  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::RemoveLanguage(int32 lcid)
0x541dd  call     bool [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditLog::get_Enabled()
0x541e2  brfalse.s loc_5425A
0x541e4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty>::.ctor()
0x541e9  stloc.0
0x541ea  newobj   instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::.ctor()
0x541ef  stloc.1
0x541f0  ldloc.1
0x541f1  ldstr    aLanguageremove// "LanguageRemoved"
0x541f6  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::set_Name(string)
0x541fb  ldloc.1
0x541fc  ldarga.s 1
0x541fe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54203  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0x54208  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5420d  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::set_OldValue(string)
0x54212  ldloc.1
0x54213  ldsfld   string [mscorlib]System.String::Empty
0x54218  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::set_NewValue(string)
0x5421d  ldloc.0
0x5421e  ldloc.1
0x5421f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty>::Add(var<u1>)
0x54224  newobj   instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditRecord::.ctor()
0x54229  stloc.2
0x5422a  ldloc.2
0x5422b  ldc.i4.s 0x30
0x5422d  box      [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation
0x54232  callvirt instance string [mscorlib]System.Object::ToString()
0x54237  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.BaseAuditRecord::set_Operation(string)
0x5423c  ldloc.2
0x5423d  ldc.i4.8
0x5423e  box      [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.ItemType
0x54243  callvirt instance string [mscorlib]System.Object::ToString()
0x54248  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointBaseAuditRecord::set_ItemType(string)
0x5424d  ldloc.2
0x5424e  ldloc.0
0x5424f  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditRecord::set_ModifiedProperties(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty>)
0x54254  ldloc.2
0x54255  call     void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditLog::WriteAudit(class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointBaseAuditRecord)
0x5425a  ldc.i4   0x3778736F
0x5425f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x54264  ldc.i4.s 0x64
0x54266  ldstr    aEndTermstoreDe// "End: TermStore.DeleteLanguage(int)"
0x5426b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x54270  ret
```
