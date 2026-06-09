# Microsoft.SharePoint.Taxonomy.Term::Delete

- ea: `0x4e000`
- end: `0x4e0c1`
- name: `Microsoft.SharePoint.Taxonomy.Term::Delete`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x2dc00`
- `0x48830`
- `0x48840`
- `0x48a60`
- `0x48ac0`
- `0x4dab0`
- `0x4e000`
- `0x4e0d0`
- `0x4eef0`
- `0x4f560`
- `0x4f6d0`
- `0x50620`
- `0x56a80`
- `0x56ab0`

## string_xrefs

- `0x4e00c`: `Begin: Term.Delete()`
- `0x4e0b6`: `End: Term.Delete()`

## pseudocode

```c

```

## disassembly

```asm
0x4e000  ldc.i4   0x3265766D
0x4e005  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4e00a  ldc.i4.s 0x64
0x4e00c  ldstr    aBeginTermDelet// "Begin: Term.Delete()"
0x4e011  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4e016  ldarg.0
0x4e017  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x4e01c  ldarg.0
0x4e01d  call     instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsReused()
0x4e022  brfalse.s loc_4E02A
0x4e024  ldarg.0
0x4e025  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsTermSet()
0x4e02a  ldarg.0
0x4e02b  call     instance void Microsoft.SharePoint.Taxonomy.Term::EnsureParentNotPinned()
0x4e030  ldc.i4.1
0x4e031  conv.i8
0x4e032  ldarg.0
0x4e033  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4e038  ldarg.0
0x4e039  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4e03e  ldarg.0
0x4e03f  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x4e044  ldarg.0
0x4e045  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e04a  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4e04f  ldc.i4.0
0x4e050  stloc.0
0x4e051  ldarg.0
0x4e052  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4e057  ldloca.s 0
0x4e059  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::RunWithElevation(bool& shouldRevert)
0x4e05e  ldarg.0
0x4e05f  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Term::get_ReusedPinnedTerms()
0x4e064  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x4e069  stloc.2
0x4e06a  br.s     loc_4E07A
0x4e06c  ldloca.s 2
0x4e06e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x4e073  stloc.1
0x4e074  ldloc.1
0x4e075  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::DeleteCore()
0x4e07a  ldloca.s 2
0x4e07c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::MoveNext()
0x4e081  brtrue.s loc_4E06C
0x4e083  leave.s  loc_4E093
0x4e085  ldloca.s 2
0x4e087  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>
0x4e08d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e092  endfinally
0x4e093  ldarg.0
0x4e094  call     instance void Microsoft.SharePoint.Taxonomy.Term::DeleteCore()
0x4e099  leave.s  loc_4E0AA
0x4e09b  ldloc.0
0x4e09c  brfalse.s loc_4E0A9
0x4e09e  ldarg.0
0x4e09f  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4e0a4  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::RevertElevation()
0x4e0a9  endfinally
0x4e0aa  ldc.i4   0x3265766E
0x4e0af  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4e0b4  ldc.i4.s 0x64
0x4e0b6  ldstr    aEndTermDelete// "End: Term.Delete()"
0x4e0bb  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4e0c0  ret
```
