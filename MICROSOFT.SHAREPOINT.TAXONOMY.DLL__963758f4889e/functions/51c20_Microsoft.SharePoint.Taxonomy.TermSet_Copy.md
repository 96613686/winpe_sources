# Microsoft.SharePoint.Taxonomy.TermSet::Copy

- ea: `0x51c20`
- end: `0x51d2c`
- name: `Microsoft.SharePoint.Taxonomy.TermSet::Copy`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x6ebd0`

## callees

- `0x24ab0`
- `0x2acd0`
- `0x2b0a0`
- `0x2dc00`
- `0x33040`
- `0x332f0`
- `0x33310`
- `0x333a0`
- `0x48830`
- `0x48840`
- `0x489e0`
- `0x48a60`
- `0x48ac0`
- `0x4dad0`
- `0x4db80`
- `0x51c20`
- `0x53360`
- `0x53740`
- `0x53940`
- `0x56c30`
- `0x579b0`

## string_xrefs

- `0x51c2c`: `Begin: TermSet.Copy()`
- `0x51c69`: `ErrorCannotCopySystemTermSet`
- `0x51d1f`: `End: TermSet.Copy()`

## pseudocode

```c

```

## disassembly

```asm
0x51c20  ldc.i4   0x32657768
0x51c25  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x51c2a  ldc.i4.s 0x64
0x51c2c  ldstr    aBeginTermsetCo// "Begin: TermSet.Copy()"
0x51c31  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51c36  ldarg.0
0x51c37  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x51c3c  ldarg.0
0x51c3d  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x51c42  ldc.i4.2
0x51c43  conv.i8
0x51c44  ldarg.0
0x51c45  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x51c4a  ldarg.0
0x51c4b  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x51c50  ldarg.0
0x51c51  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x51c56  ldarg.0
0x51c57  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x51c5c  ldarg.0
0x51c5d  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x51c62  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_Type()
0x51c67  brfalse.s loc_51C79
0x51c69  ldstr    aErrorcannotcop// "ErrorCannotCopySystemTermSet"
0x51c6e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x51c73  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x51c78  throw
0x51c79  ldarg.0
0x51c7a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.SharePoint.Taxonomy.TermSet::get_Names()
0x51c7f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x51c84  stloc.0
0x51c85  ldloc.0
0x51c86  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Keys()
0x51c8b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x51c90  stloc.1
0x51c91  ldloc.1
0x51c92  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int32>::GetEnumerator()
0x51c97  stloc.s  5
0x51c99  br.s     loc_51CBD
0x51c9b  ldloca.s 5
0x51c9d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::get_Current()
0x51ca2  stloc.2
0x51ca3  ldloc.0
0x51ca4  ldloc.2
0x51ca5  ldloc.0
0x51ca6  ldloc.2
0x51ca7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x51cac  ldarg.0
0x51cad  ldloc.2
0x51cae  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.TermSet::GetSiblingNames(int32 lcid)
0x51cb3  call     string Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetCopiedName(string nameToCopy, class [mscorlib]System.Collections.Generic.List`1<string> existingNames)
0x51cb8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::set_Item(var<u1>, !!T0)
0x51cbd  ldloca.s 5
0x51cbf  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::MoveNext()
0x51cc4  brtrue.s loc_51C9B
0x51cc6  leave.s  loc_51CD6
0x51cc8  ldloca.s 5
0x51cca  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>
0x51cd0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51cd5  endfinally
0x51cd6  ldloc.0
0x51cd7  call     string Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::GetAllNames(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> updatedNames)
0x51cdc  stloc.3
0x51cdd  ldarg.0
0x51cde  ldloc.3
0x51cdf  ldarg.0
0x51ce0  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x51ce5  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_Owner()
0x51cea  ldarg.0
0x51ceb  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x51cf0  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_CustomSortOrder()
0x51cf5  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermSet::CopyTermSetInSandbox(string allNames, string owner, string customSortOrder)
0x51cfa  stloc.s  4
0x51cfc  ldarg.0
0x51cfd  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x51d02  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x51d07  ldloc.s  4
0x51d09  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x51d0e  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x51d13  ldc.i4   0x32657769
0x51d18  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x51d1d  ldc.i4.s 0x64
0x51d1f  ldstr    aEndTermsetCopy// "End: TermSet.Copy()"
0x51d24  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51d29  ldloc.s  4
0x51d2b  ret
```
