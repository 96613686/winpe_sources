# Microsoft.SharePoint.Taxonomy.Term::Copy

- ea: `0x4de70`
- end: `0x4df26`
- name: `Microsoft.SharePoint.Taxonomy.Term::Copy`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x6ebd0`

## callees

- `0x2dc00`
- `0x48830`
- `0x48840`
- `0x48a60`
- `0x48ac0`
- `0x4d2a0`
- `0x4d530`
- `0x4dad0`
- `0x4de70`
- `0x4f1e0`
- `0x4f560`
- `0x4f6d0`
- `0x4fdd0`
- `0x50620`

## string_xrefs

- `0x4de7c`: `Begin: Term.Copy(bool)`
- `0x4df1a`: `End: Term.Copy(bool)`

## pseudocode

```c

```

## disassembly

```asm
0x4de70  ldc.i4   0x32657665
0x4de75  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4de7a  ldc.i4.s 0x64
0x4de7c  ldstr    aBeginTermCopyB// "Begin: Term.Copy(bool)"
0x4de81  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4de86  ldarg.0
0x4de87  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x4de8c  ldarg.0
0x4de8d  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x4de92  ldarg.0
0x4de93  call     instance void Microsoft.SharePoint.Taxonomy.Term::EnsureParentNotPinned()
0x4de98  ldc.i4.1
0x4de99  conv.i8
0x4de9a  ldarg.0
0x4de9b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4dea0  ldarg.0
0x4dea1  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4dea6  ldarg.0
0x4dea7  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x4deac  ldarg.0
0x4dead  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4deb2  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4deb7  ldarg.0
0x4deb8  ldarg.0
0x4deb9  ldarg.0
0x4deba  callvirt instance string Microsoft.SharePoint.Taxonomy.TermSetItem::get_Owner()
0x4debf  ldarg.1
0x4dec0  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::CopyTermInSandbox(class Microsoft.SharePoint.Taxonomy.Term sourceTerm, string owner, bool doCopyChildren)
0x4dec5  stloc.0
0x4dec6  ldarg.0
0x4dec7  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x4decc  brfalse.s loc_4DF0E
0x4dece  ldarg.0
0x4decf  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x4ded4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Term::get_ReusedPinnedTerms()
0x4ded9  stloc.1
0x4deda  ldloc.1
0x4dedb  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x4dee0  stloc.3
0x4dee1  br.s     loc_4DEF5
0x4dee3  ldloca.s 3
0x4dee5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x4deea  stloc.2
0x4deeb  ldloc.2
0x4deec  ldloc.0
0x4deed  ldarg.1
0x4deee  ldc.i4.1
0x4deef  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::ReuseTermCore(class Microsoft.SharePoint.Taxonomy.Term sourceTerm, bool reuseBranch, bool withPinning)
0x4def4  pop
0x4def5  ldloca.s 3
0x4def7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::MoveNext()
0x4defc  brtrue.s loc_4DEE3
0x4defe  leave.s  loc_4DF0E
0x4df00  ldloca.s 3
0x4df02  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>
0x4df08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4df0d  endfinally
0x4df0e  ldc.i4   0x32657666
0x4df13  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4df18  ldc.i4.s 0x64
0x4df1a  ldstr    aEndTermCopyBoo// "End: Term.Copy(bool)"
0x4df1f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4df24  ldloc.0
0x4df25  ret
```
