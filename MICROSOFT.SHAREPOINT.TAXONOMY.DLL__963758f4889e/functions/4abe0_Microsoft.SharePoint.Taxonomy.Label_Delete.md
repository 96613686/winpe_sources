# Microsoft.SharePoint.Taxonomy.Label::Delete

- ea: `0x4abe0`
- end: `0x4ac98`
- name: `Microsoft.SharePoint.Taxonomy.Label::Delete`
- size: `184`
- prototype: ``
- caller_count: `6`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x6890`
- `0x6b40`
- `0x9110`
- `0x93c0`
- `0x61650`
- `0x62270`

## callees

- `0x2acd0`
- `0x31030`
- `0x48ac0`
- `0x4abe0`
- `0x4ad00`
- `0x4ad10`
- `0x4ad90`
- `0x4e260`
- `0x4ef50`
- `0x4f680`
- `0x4f6a0`
- `0x50680`
- `0x55440`
- `0x579b0`

## string_xrefs

- `0x4ac19`: `ErrorCannotDeleteDefaultLabel`
- `0x4ac42`: `ErrorCannotDeleteNonLastDefaultLabel`
- `0x4ac65`: `ErrorCannotDeleteLastLabel`

## pseudocode

```c

```

## disassembly

```asm
0x4abe0  ldarg.0
0x4abe1  ldfld    class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Label::term
0x4abe6  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::EnsureNotPinned()
0x4abeb  ldarg.0
0x4abec  ldfld    class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Label::term
0x4abf1  ldc.i4.1
0x4abf2  conv.i8
0x4abf3  ldc.i4.1
0x4abf4  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, bool checkPermissionsOnSourceTerm)
0x4abf9  ldarg.0
0x4abfa  call     instance bool Microsoft.SharePoint.Taxonomy.Label::get_IsDefaultForLanguage()
0x4abff  brfalse.s loc_4AC52
0x4ac01  ldarg.0
0x4ac02  call     instance int32 Microsoft.SharePoint.Taxonomy.Label::get_Language()
0x4ac07  ldarg.0
0x4ac08  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Label::get_Term()
0x4ac0d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4ac12  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x4ac17  bne.un.s loc_4AC29
0x4ac19  ldstr    aErrorcannotdel_0// "ErrorCannotDeleteDefaultLabel"
0x4ac1e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4ac23  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4ac28  throw
0x4ac29  ldarg.0
0x4ac2a  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Label::get_Term()
0x4ac2f  ldarg.0
0x4ac30  ldfld    int32 Microsoft.SharePoint.Taxonomy.Label::lcid
0x4ac35  callvirt instance class Microsoft.SharePoint.Taxonomy.LabelCollection Microsoft.SharePoint.Taxonomy.Term::GetAllLabels(int32 lcid)
0x4ac3a  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Label>::get_Count()
0x4ac3f  ldc.i4.1
0x4ac40  ble.s    loc_4AC52
0x4ac42  ldstr    aErrorcannotdel_1// "ErrorCannotDeleteNonLastDefaultLabel"
0x4ac47  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4ac4c  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4ac51  throw
0x4ac52  ldarg.0
0x4ac53  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Label::get_Term()
0x4ac58  callvirt instance class Microsoft.SharePoint.Taxonomy.LabelCollection Microsoft.SharePoint.Taxonomy.Term::get_Labels()
0x4ac5d  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Label>::get_Count()
0x4ac62  ldc.i4.1
0x4ac63  bgt.s    loc_4AC75
0x4ac65  ldstr    aErrorcannotdel_2// "ErrorCannotDeleteLastLabel"
0x4ac6a  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4ac6f  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4ac74  throw
0x4ac75  ldarg.0
0x4ac76  ldfld    class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Label::term
0x4ac7b  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x4ac80  ldarg.0
0x4ac81  ldfld    string Microsoft.SharePoint.Taxonomy.Label::labelValue
0x4ac86  ldarg.0
0x4ac87  ldfld    int32 Microsoft.SharePoint.Taxonomy.Label::lcid
0x4ac8c  ldarg.0
0x4ac8d  ldfld    bool Microsoft.SharePoint.Taxonomy.Label::isDefault
0x4ac92  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::DeleteLabel(string labelName, int32 lcid, bool isDefault)
0x4ac97  ret
```
