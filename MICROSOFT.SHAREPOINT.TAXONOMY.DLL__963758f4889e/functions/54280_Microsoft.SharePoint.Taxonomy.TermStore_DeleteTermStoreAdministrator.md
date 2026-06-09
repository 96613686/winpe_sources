# Microsoft.SharePoint.Taxonomy.TermStore::DeleteTermStoreAdministrator

- ea: `0x54280`
- end: `0x54344`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::DeleteTermStoreAdministrator`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x5cf0`
- `0x8780`

## callees

- `0x2acd0`
- `0x33780`
- `0x54280`
- `0x55e90`
- `0x56c80`

## string_xrefs

- `0x542d4`: `AdministratorRemoved`
- `0x5432e`: `ErrorUnknownUserForTermStoreAdminDelete`

## pseudocode

```c

```

## disassembly

```asm
0x54280  ldarg.0
0x54281  ldc.i4.s 0x20
0x54283  conv.i8
0x54284  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions)
0x54289  ldarg.0
0x5428a  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x5428f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_Acl()
0x54294  ldarg.1
0x54295  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::get_Item(!!T0)
0x5429a  stloc.0
0x5429b  ldloc.0
0x5429c  brfalse  loc_5432E
0x542a1  ldloc.0
0x542a2  callvirt instance var<u1> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::get_GrantRightsMask()
0x542a7  ldc.i4   0x110
0x542ac  conv.i8
0x542ad  bne.un.s loc_5432E
0x542af  ldarg.0
0x542b0  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x542b5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_Acl()
0x542ba  ldloc.0
0x542bb  callvirt instance void class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::Remove(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<var<u1>>)
0x542c0  call     bool [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditLog::get_Enabled()
0x542c5  brfalse.s loc_54343
0x542c7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty>::.ctor()
0x542cc  stloc.1
0x542cd  newobj   instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::.ctor()
0x542d2  stloc.2
0x542d3  ldloc.2
0x542d4  ldstr    aAdministratorr// "AdministratorRemoved"
0x542d9  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::set_Name(string)
0x542de  ldloc.2
0x542df  ldarg.1
0x542e0  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::set_OldValue(string)
0x542e5  ldloc.2
0x542e6  ldsfld   string [mscorlib]System.String::Empty
0x542eb  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty::set_NewValue(string)
0x542f0  ldloc.1
0x542f1  ldloc.2
0x542f2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty>::Add(var<u1>)
0x542f7  newobj   instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditRecord::.ctor()
0x542fc  stloc.3
0x542fd  ldloc.3
0x542fe  ldc.i4.s 0xC
0x54300  box      [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation
0x54305  callvirt instance string [mscorlib]System.Object::ToString()
0x5430a  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.BaseAuditRecord::set_Operation(string)
0x5430f  ldloc.3
0x54310  ldc.i4.8
0x54311  box      [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.ItemType
0x54316  callvirt instance string [mscorlib]System.Object::ToString()
0x5431b  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointBaseAuditRecord::set_ItemType(string)
0x54320  ldloc.3
0x54321  ldloc.1
0x54322  callvirt instance void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditRecord::set_ModifiedProperties(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.ModifiedProperty>)
0x54327  ldloc.3
0x54328  call     void [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditLog::WriteAudit(class [Microsoft.SharePoint]Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointBaseAuditRecord)
0x5432d  ret
0x5432e  ldstr    aErrorunknownus_2// "ErrorUnknownUserForTermStoreAdminDelete"
0x54333  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x54338  ldstr    aPrincipalname// "principalName"
0x5433d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x54342  throw
0x54343  ret
```
