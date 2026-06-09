# Microsoft.SharePoint.Taxonomy.ImportManager::ImportTermSet

- ea: `0x4a280`
- end: `0x4a51a`
- name: `Microsoft.SharePoint.Taxonomy.ImportManager::ImportTermSet`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0xce0`

## callees

- `0x2acd0`
- `0x2ad40`
- `0x2dc00`
- `0x48780`
- `0x48830`
- `0x497b0`
- `0x4a1a0`
- `0x4a240`
- `0x4a280`
- `0x4a540`
- `0x4a550`
- `0x4a640`
- `0x4a7c0`
- `0x4aae0`
- `0x53f80`
- `0x55440`
- `0x579b0`

## string_xrefs

- `0x4a2af`: `reader`
- `0x4a37e`: `reader`
- `0x4a2d7`: `ErrorCannotCreateTermSetInSystemGroup`
- `0x4a28c`: `Begin: ImportManager.ImportTermSet(Group, TextReader, Boolean&, String&)`
- `0x4a457`: `Error encountered during term set import`
- `0x4a50b`: `End: ImportManager.ImportTermSet(Group, TextReader, Boolean&, String&)`

## pseudocode

```c

```

## disassembly

```asm
0x4a280  ldc.i4   0x37323970
0x4a285  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a28a  ldc.i4.s 0x64
0x4a28c  ldstr    aBeginImportman// "Begin: ImportManager.ImportTermSet(Grou"...
0x4a291  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4a296  ldarg.s  4
0x4a298  ldsfld   string [mscorlib]System.String::Empty
0x4a29d  stind.ref
0x4a29e  ldarg.1
0x4a29f  brtrue.s loc_4A2AC
0x4a2a1  ldstr    aParentgroup// "parentGroup"
0x4a2a6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a2ab  throw
0x4a2ac  ldarg.2
0x4a2ad  brtrue.s loc_4A2BA
0x4a2af  ldstr    aReader// "reader"
0x4a2b4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a2b9  throw
0x4a2ba  ldc.i4.2
0x4a2bb  conv.i8
0x4a2bc  ldarg.1
0x4a2bd  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4a2c2  ldarg.0
0x4a2c3  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.ImportManager::get_TermStore()
0x4a2c8  ldarg.1
0x4a2c9  ldnull
0x4a2ca  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4a2cf  ldarg.1
0x4a2d0  callvirt instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSystemGroup()
0x4a2d5  brfalse.s loc_4A2E7
0x4a2d7  ldstr    aErrorcannotcre// "ErrorCannotCreateTermSetInSystemGroup"
0x4a2dc  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4a2e1  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4a2e6  throw
0x4a2e7  ldnull
0x4a2e8  stloc.0
0x4a2e9  ldarg.0
0x4a2ea  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.ImportManager::get_TermStore()
0x4a2ef  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x4a2f4  stloc.1
0x4a2f5  ldc.i4.m1
0x4a2f6  stloc.2
0x4a2f7  ldarg.3
0x4a2f8  ldc.i4.1
0x4a2f9  stind.i1
0x4a2fa  ldc.i4.1
0x4a2fb  stloc.3
0x4a2fc  ldnull
0x4a2fd  stloc.s  4
0x4a2ff  br       loc_4A3FA
0x4a304  ldloc.2
0x4a305  ldc.i4.1
0x4a306  add.ovf
0x4a307  stloc.2
0x4a308  ldloc.2
0x4a309  brtrue.s loc_4A389
0x4a30b  ldc.i4.1
0x4a30c  newarr   [mscorlib]System.String
0x4a311  stloc.s  0xB
0x4a313  ldloc.s  0xB
0x4a315  ldc.i4.0
0x4a316  ldarg.0
0x4a317  call     instance string Microsoft.SharePoint.Taxonomy.ImportManager::get_DelimiterAsString()
0x4a31c  stelem.ref
0x4a31d  ldloc.s  0xB
0x4a31f  stloc.s  5
0x4a321  ldc.i4.1
0x4a322  newarr   [mscorlib]System.String
0x4a327  stloc.s  0xC
0x4a329  ldloc.s  0xC
0x4a32b  ldc.i4.0
0x4a32c  ldstr    asc_7EF00// ","
0x4a331  stelem.ref
0x4a332  ldloc.s  0xC
0x4a334  stloc.s  6
0x4a336  ldloc.s  4
0x4a338  ldloc.s  5
0x4a33a  ldc.i4.0
0x4a33b  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x4a340  ldlen
0x4a341  conv.i4
0x4a342  stloc.s  7
0x4a344  ldloc.s  4
0x4a346  ldloc.s  6
0x4a348  ldc.i4.0
0x4a349  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x4a34e  ldlen
0x4a34f  conv.i4
0x4a350  stloc.s  8
0x4a352  ldloc.s  8
0x4a354  ldloc.s  7
0x4a356  ble.s    loc_4A362
0x4a358  ldarg.0
0x4a359  ldloc.s  6
0x4a35b  ldc.i4.0
0x4a35c  ldelem.ref
0x4a35d  call     instance void Microsoft.SharePoint.Taxonomy.ImportManager::set_DelimiterAsString(string value)
0x4a362  ldloc.s  4
0x4a364  ldarg.0
0x4a365  call     instance string Microsoft.SharePoint.Taxonomy.ImportManager::get_DelimiterAsString()
0x4a36a  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4a36f  brtrue   loc_4A3FA
0x4a374  ldstr    aErrorinvalidim// "ErrorInvalidImportCsvFormat"
0x4a379  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4a37e  ldstr    aReader// "reader"
0x4a383  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x4a388  throw
0x4a389  ldloc.2
0x4a38a  ldc.i4.1
0x4a38b  ble.s    loc_4A39B
0x4a38d  ldloc.s  4
0x4a38f  callvirt instance string [mscorlib]System.String::Trim()
0x4a394  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a399  brtrue.s loc_4A3FA
0x4a39b  ldarg.0
0x4a39c  ldloc.s  4
0x4a39e  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.ImportManager::ParseLineIntoEntries(string line)
0x4a3a3  stloc.s  9
0x4a3a5  ldloc.0
0x4a3a6  brtrue.s loc_4A3BF
0x4a3a8  ldloc.2
0x4a3a9  ldc.i4.1
0x4a3aa  beq.s    loc_4A3B4
0x4a3ac  ldnull
0x4a3ad  stloc.s  0xA
0x4a3af  leave    loc_4A517
0x4a3b4  ldarg.1
0x4a3b5  ldloc.s  9
0x4a3b7  ldarg.s  4
0x4a3b9  call     class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.ImportManager::CreateEmptyImportTermSet(class Microsoft.SharePoint.Taxonomy.Group parentGroup, class [mscorlib]System.Collections.Generic.List`1<string> entries, [out] string& errorMessage)
0x4a3be  stloc.0
0x4a3bf  ldarg.s  4
0x4a3c1  ldind.ref
0x4a3c2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a3c7  brfalse.s loc_4A3FA
0x4a3c9  ldarg.0
0x4a3ca  ldloc.1
0x4a3cb  ldloc.2
0x4a3cc  ldloc.s  9
0x4a3ce  call     instance int32 Microsoft.SharePoint.Taxonomy.ImportManager::GetImportLcid(int32 lcid, int32 lineNum, class [mscorlib]System.Collections.Generic.List`1<string> entries)
0x4a3d3  stloc.1
0x4a3d4  ldloc.s  9
0x4a3d6  ldloc.0
0x4a3d7  ldloc.1
0x4a3d8  ldloc.2
0x4a3d9  ldc.i4.1
0x4a3da  add.ovf
0x4a3db  call     bool Microsoft.SharePoint.Taxonomy.ImportManager::AddTermToImportTermSet(class [mscorlib]System.Collections.Generic.List`1<string> entries, class Microsoft.SharePoint.Taxonomy.TermSet importTermSet, int32 lcid, int32 lineNumber)
0x4a3e0  brtrue.s loc_4A3E5
0x4a3e2  ldarg.3
0x4a3e3  ldc.i4.0
0x4a3e4  stind.i1
0x4a3e5  ldloc.2
0x4a3e6  ldarg.0
0x4a3e7  ldfld    int32 Microsoft.SharePoint.Taxonomy.ImportManager::batchSize
0x4a3ec  rem
0x4a3ed  brtrue.s loc_4A3FA
0x4a3ef  ldarg.0
0x4a3f0  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.ImportManager::get_TermStore()
0x4a3f5  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x4a3fa  ldarg.s  4
0x4a3fc  ldind.ref
0x4a3fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a402  brfalse.s loc_4A412
0x4a404  ldarg.2
0x4a405  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0x4a40a  dup
0x4a40b  stloc.s  4
0x4a40d  brtrue   loc_4A304
0x4a412  ldloc.3
0x4a413  brfalse.s loc_4A434
0x4a415  ldarg.s  4
0x4a417  ldind.ref
0x4a418  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a41d  brfalse.s loc_4A434
0x4a41f  ldloc.2
0x4a420  ldarg.0
0x4a421  ldfld    int32 Microsoft.SharePoint.Taxonomy.ImportManager::batchSize
0x4a426  rem
0x4a427  brfalse.s loc_4A434
0x4a429  ldarg.0
0x4a42a  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.ImportManager::get_TermStore()
0x4a42f  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x4a434  leave.s  loc_4A43B
0x4a436  pop
0x4a437  ldc.i4.0
0x4a438  stloc.3
0x4a439  leave.s  loc_4A43B
0x4a43b  ldloc.3
0x4a43c  brfalse.s loc_4A44B
0x4a43e  ldarg.s  4
0x4a440  ldind.ref
0x4a441  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a446  brtrue   loc_4A4FF
0x4a44b  ldc.i4   0x37323971
0x4a450  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a455  ldc.i4.s 0xA
0x4a457  ldstr    aErrorEncounter_1// "Error encountered during term set impor"...
0x4a45c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4a461  ldarg.s  4
0x4a463  ldind.ref
0x4a464  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a469  brtrue.s loc_4A47C
0x4a46b  ldarg.s  4
0x4a46d  dup
0x4a46e  ldind.ref
0x4a46f  ldc.i4.s 0xA
0x4a471  box      [mscorlib]System.Char
0x4a476  call     string [mscorlib]System.String::Concat(object, object)
0x4a47b  stind.ref
0x4a47c  ldloc.0
0x4a47d  brfalse.s loc_4A4D5
0x4a47f  ldloc.0
0x4a480  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x4a485  ldarg.0
0x4a486  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.ImportManager::get_TermStore()
0x4a48b  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x4a490  leave.s  loc_4A4FF
0x4a492  pop
0x4a493  ldc.i4   0x37323972
0x4a498  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a49d  ldc.i4.s 0xA
0x4a49f  ldstr    aErrorEncounter_2// "Error encountered while trying to clean"...
0x4a4a4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4a4a9  ldarg.s  4
0x4a4ab  dup
0x4a4ac  ldind.ref
0x4a4ad  ldstr    aErrortermsetim// "ErrorTermSetImportFailedAndCleanupFaile"...
0x4a4b2  ldc.i4.1
0x4a4b3  newarr   [mscorlib]System.Object
0x4a4b8  stloc.s  0xD
0x4a4ba  ldloc.s  0xD
0x4a4bc  ldc.i4.0
0x4a4bd  ldloc.2
0x4a4be  ldc.i4.1
0x4a4bf  add.ovf
0x4a4c0  box      [mscorlib]System.Int32
0x4a4c5  stelem.ref
0x4a4c6  ldloc.s  0xD
0x4a4c8  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x4a4cd  call     string [mscorlib]System.String::Concat(string, string)
0x4a4d2  stind.ref
0x4a4d3  leave.s  loc_4A4FF
0x4a4d5  ldarg.s  4
0x4a4d7  dup
0x4a4d8  ldind.ref
0x4a4d9  ldstr    aErrortermsetim_0// "ErrorTermSetImportFailed"
0x4a4de  ldc.i4.1
0x4a4df  newarr   [mscorlib]System.Object
0x4a4e4  stloc.s  0xE
0x4a4e6  ldloc.s  0xE
0x4a4e8  ldc.i4.0
0x4a4e9  ldloc.2
0x4a4ea  ldc.i4.1
0x4a4eb  add.ovf
0x4a4ec  box      [mscorlib]System.Int32
0x4a4f1  stelem.ref
0x4a4f2  ldloc.s  0xE
0x4a4f4  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x4a4f9  call     string [mscorlib]System.String::Concat(string, string)
0x4a4fe  stind.ref
0x4a4ff  ldc.i4   0x37323973
0x4a504  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a509  ldc.i4.s 0x64
0x4a50b  ldstr    aEndImportmanag// "End: ImportManager.ImportTermSet(Group,"...
0x4a510  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4a515  ldloc.0
0x4a516  ret
0x4a517  ldloc.s  0xA
0x4a519  ret
```
