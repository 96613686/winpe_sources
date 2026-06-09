# Microsoft.SharePoint.Taxonomy.Term::PrepareForDelete

- ea: `0x4ff50`
- end: `0x500cf`
- name: `Microsoft.SharePoint.Taxonomy.Term::PrepareForDelete`
- size: `383`
- prototype: ``
- caller_count: `3`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x4d9e0`
- `0x4e0d0`
- `0x4ff10`

## callees

- `0x2acd0`
- `0x2b0a0`
- `0x2ecb0`
- `0x32130`
- `0x325b0`
- `0x32ff0`
- `0x338d0`
- `0x487f0`
- `0x488e0`
- `0x48920`
- `0x48980`
- `0x489e0`
- `0x48ac0`
- `0x48af0`
- `0x4d7d0`
- `0x4db80`
- `0x4eef0`
- `0x4ef30`
- `0x4f3a0`
- `0x4f560`
- `0x4ff50`
- `0x50570`
- `0x50620`
- `0x50680`
- `0x536f0`
- `0x55830`
- `0x56c30`
- `0x56c80`
- `0x579b0`

## string_xrefs

- `0x5007d`: `ErrorCannotDeleteReusedTermInOrphanTermSet`
- `0x500ac`: `Trying to move the source Term '{0}' to Orphaned Terms TermSet`

## pseudocode

```c

```

## disassembly

```asm
0x4ff50  ldarg.0
0x4ff51  call     instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x4ff56  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x4ff5b  ldc.i4.1
0x4ff5c  bne.un   loc_5002D
0x4ff61  ldarg.0
0x4ff62  call     instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x4ff67  ldc.i4.0
0x4ff68  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x4ff6d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4ff72  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.TermSet::get_Type()
0x4ff77  ldc.i4.2
0x4ff78  bne.un   loc_5002D
0x4ff7d  ldarg.0
0x4ff7e  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4ff83  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::get_OrphanedTermsTermSet()
0x4ff88  stloc.0
0x4ff89  ldarg.0
0x4ff8a  call     instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x4ff8f  ldc.i4.0
0x4ff90  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x4ff95  stloc.1
0x4ff96  ldarg.0
0x4ff97  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginUpdateWithoutAclCheck()
0x4ff9c  ldloc.1
0x4ff9d  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsSourceTerm()
0x4ffa2  brfalse.s loc_4FFE2
0x4ffa4  ldarg.0
0x4ffa5  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership Microsoft.SharePoint.Taxonomy.Term::get_Membership()
0x4ffaa  ldc.i4.1
0x4ffab  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership::set_IsSource(bool value)
0x4ffb0  ldarg.0
0x4ffb1  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x4ffb6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership> Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::get_Memberships()
0x4ffbb  ldloc.0
0x4ffbc  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_InternalId()
0x4ffc1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>::get_Item(void)
0x4ffc6  ldc.i4.0
0x4ffc7  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership::set_IsSource(bool value)
0x4ffcc  ldarg.0
0x4ffcd  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4ffd2  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x4ffd7  ldarg.0
0x4ffd8  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x4ffdd  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x4ffe2  ldarg.0
0x4ffe3  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginDeleteWithoutAclCheck()
0x4ffe8  ldarg.0
0x4ffe9  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x4ffee  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership> Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::get_Memberships()
0x4fff3  ldloc.0
0x4fff4  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_InternalId()
0x4fff9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>::Remove(var<u1>)
0x4fffe  pop
0x4ffff  ldloc.0
0x50000  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginMembershipUpdate()
0x50005  ldloc.0
0x50006  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x5000b  ldarg.0
0x5000c  call     instance int32 Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_InternalId()
0x50011  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::RemoveRootTermId(int32 termId)
0x50016  ldarg.0
0x50017  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x5001c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x50021  ldloc.1
0x50022  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x50027  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x5002c  ret
0x5002d  ldarg.0
0x5002e  call     instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsReused()
0x50033  brfalse  loc_500C8
0x50038  ldarg.0
0x50039  call     instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsSourceTerm()
0x5003e  brfalse  loc_500C8
0x50043  ldarg.0
0x50044  call     instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x50049  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x5004e  ldarg.0
0x5004f  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Term::get_ReusedPinnedTerms()
0x50054  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x50059  beq.s    loc_500C8
0x5005b  ldarg.0
0x5005c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x50061  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_UniqueId()
0x50066  ldarg.0
0x50067  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x5006c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x50071  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_OrphanedTermSetId()
0x50076  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5007b  brfalse.s loc_5008D
0x5007d  ldstr    aErrorcannotdel_3// "ErrorCannotDeleteReusedTermInOrphanTerm"...
0x50082  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x50087  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x5008c  throw
0x5008d  ldarg.0
0x5008e  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x50093  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::get_OrphanedTermsTermSet()
0x50098  ldarg.0
0x50099  ldc.i4.1
0x5009a  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::ReuseTermWithoutValidation(class Microsoft.SharePoint.Taxonomy.Term sourceTerm, bool reassignSourceTerm)
0x5009f  stloc.2
0x500a0  ldc.i4   0x31796972
0x500a5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x500aa  ldc.i4.s 0x32
0x500ac  ldstr    aTryingToMoveTh// "Trying to move the source Term '{0}' to"...
0x500b1  ldc.i4.1
0x500b2  newarr   [mscorlib]System.Object
0x500b7  stloc.3
0x500b8  ldloc.3
0x500b9  ldc.i4.0
0x500ba  ldloc.2
0x500bb  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x500c0  stelem.ref
0x500c1  ldloc.3
0x500c2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x500c7  ret
0x500c8  ldarg.0
0x500c9  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginMembershipUpdate()
0x500ce  ret
```
