# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetSuggestionsInternal

- ea: `0x6b460`
- end: `0x6b6ca`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetSuggestionsInternal`
- size: `618`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x69710`
- `0x6b420`

## callees

- `0x2acd0`
- `0x48790`
- `0x4bad0`
- `0x4cb30`
- `0x4cc10`
- `0x57910`
- `0x6b330`
- `0x6b460`
- `0x6d530`
- `0x713f0`
- `0x71400`
- `0x71420`
- `0x71430`
- `0x714a0`
- `0x714c0`
- `0x714e0`
- `0x71500`
- `0x71510`
- `0x71530`
- `0x715b0`
- `0x71630`
- `0x71640`
- `0x71920`
- `0x719a0`
- `0x719b0`

## string_xrefs

- `0x6b63a`: `CreateNewKeyword`
- `0x6b663`: `CreateNewKeywordDescription`

## pseudocode

```c

```

## disassembly

```asm
0x6b460  ldarg.0
0x6b461  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItem::NormalizeName(string name)
0x6b466  starg.s  0
0x6b468  ldarg.1
0x6b469  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6b46e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject>::.ctor()
0x6b473  stloc.0
0x6b474  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x6b479  stloc.1
0x6b47a  ldc.i4.0
0x6b47b  stloc.2
0x6b47c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6b481  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6b486  ldc.i4.0
0x6b487  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, bool updateCache)
0x6b48c  stloc.3
0x6b48d  ldarg.s  5
0x6b48f  brfalse.s loc_6B49E
0x6b491  ldloc.3
0x6b492  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x6b497  stloc.s  4
0x6b499  br       loc_6B53B
0x6b49e  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x6b4a3  stloc.s  5
0x6b4a5  ldarg.2
0x6b4a6  ldc.i4.1
0x6b4a7  newarr   [mscorlib]System.Char
0x6b4ac  stloc.s  0x11
0x6b4ae  ldloc.s  0x11
0x6b4b0  ldc.i4.0
0x6b4b1  ldc.i4.s 0x3B
0x6b4b3  stelem.i2
0x6b4b4  ldloc.s  0x11
0x6b4b6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x6b4bb  stloc.s  6
0x6b4bd  ldc.i4.0
0x6b4be  stloc.s  7
0x6b4c0  br.s     loc_6B52A
0x6b4c2  ldloca.s 8
0x6b4c4  ldloc.s  6
0x6b4c6  ldloc.s  7
0x6b4c8  ldelem.ref
0x6b4c9  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6b4ce  ldloc.s  8
0x6b4d0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6b4d5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6b4da  brfalse.s loc_6B4F0
0x6b4dc  ldloc.s  5
0x6b4de  ldloc.3
0x6b4df  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x6b4e4  ldloc.s  8
0x6b4e6  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.IndexedCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Item(!!T0)
0x6b4eb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>)
0x6b4f0  leave.s  loc_6B524
0x6b4f2  pop
0x6b4f3  ldc.i4   0x62733036
0x6b4f8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6b4fd  ldc.i4.s 0xA
0x6b4ff  ldstr    aGetsuggestionC// "GetSuggestion contain malformed term st"...
0x6b504  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6b509  leave.s  loc_6B524
0x6b50b  pop
0x6b50c  ldc.i4   0x62733037
0x6b511  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6b516  ldc.i4.s 0xA
0x6b518  ldstr    aGetsuggestionS// "GetSuggestion session does not contain "...
0x6b51d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6b522  leave.s  loc_6B524
0x6b524  ldloc.s  7
0x6b526  ldc.i4.1
0x6b527  add.ovf
0x6b528  stloc.s  7
0x6b52a  ldloc.s  7
0x6b52c  ldloc.s  6
0x6b52e  ldlen
0x6b52f  conv.i4
0x6b530  blt.s    loc_6B4C2
0x6b532  ldloc.s  5
0x6b534  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreCollection::.ctor(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Taxonomy.TermStore> collection)
0x6b539  stloc.s  4
0x6b53b  ldarg.3
0x6b53c  ldc.i4.1
0x6b53d  newarr   [mscorlib]System.Char
0x6b542  stloc.s  0x12
0x6b544  ldloc.s  0x12
0x6b546  ldc.i4.0
0x6b547  ldc.i4.s 0x3B
0x6b549  stelem.i2
0x6b54a  ldloc.s  0x12
0x6b54c  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x6b551  stloc.s  9
0x6b553  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x6b558  stloc.s  0xA
0x6b55a  ldc.i4.0
0x6b55b  stloc.s  0xB
0x6b55d  br.s     loc_6B5A4
0x6b55f  ldloca.s 0xC
0x6b561  ldloc.s  9
0x6b563  ldloc.s  0xB
0x6b565  ldelem.ref
0x6b566  callvirt instance string [mscorlib]System.String::Trim()
0x6b56b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6b570  ldloc.s  0xC
0x6b572  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::HashTagsTermSetId
0x6b577  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6b57c  brfalse.s loc_6B590
0x6b57e  ldloc.s  4
0x6b580  callvirt instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_InternalCollection()
0x6b585  ldloc.3
0x6b586  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::get_DefaultKeywordsTermStore()
0x6b58b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>)
0x6b590  ldloc.s  0xA
0x6b592  ldloc.s  0xC
0x6b594  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x6b599  leave.s  loc_6B59E
0x6b59b  pop
0x6b59c  leave.s  loc_6B59E
0x6b59e  ldloc.s  0xB
0x6b5a0  ldc.i4.1
0x6b5a1  add.ovf
0x6b5a2  stloc.s  0xB
0x6b5a4  ldloc.s  0xB
0x6b5a6  ldloc.s  9
0x6b5a8  ldlen
0x6b5a9  conv.i4
0x6b5aa  blt.s    loc_6B55F
0x6b5ac  ldloc.3
0x6b5ad  ldloc.s  4
0x6b5af  ldarg.1
0x6b5b0  ldarg.0
0x6b5b1  ldarg.s  4
0x6b5b3  ldc.i4.1
0x6b5b4  ldarg.s  6
0x6b5b6  ldarg.s  7
0x6b5b8  ldarg.s  8
0x6b5ba  ldarg.s  9
0x6b5bc  ldarg.s  0xA
0x6b5be  ldarg.s  0xB
0x6b5c0  ldloc.1
0x6b5c1  ldloc.s  0xA
0x6b5c3  ldloc.2
0x6b5c4  ldarg.s  0xC
0x6b5c6  ldloc.0
0x6b5c7  call     bool Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetSuggestionsFromStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, class Microsoft.SharePoint.Taxonomy.TermStoreCollection termStores, int32 lcid, string start, valuetype [mscorlib]System.Guid anchorId, bool isSynonym, bool isSpanTermSets, bool isIncludeUnavailable, bool isIncludeDeprecated, bool isAddTerms, bool isIncludePathData, bool excludeKeyword, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> foundItems, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> tsGuidList, bool foundMatchingKeyword, valuetype [mscorlib]System.Guid excludedTermset, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject> groups)
0x6b5cc  stloc.2
0x6b5cd  ldarg.s  9
0x6b5cf  brfalse  loc_6B6B8
0x6b5d4  ldarg.s  6
0x6b5d6  brtrue.s loc_6B5E5
0x6b5d8  ldloc.s  0xA
0x6b5da  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x6b5df  ldc.i4.1
0x6b5e0  bne.un   loc_6B6B8
0x6b5e5  ldloc.0
0x6b5e6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject>::get_Count()
0x6b5eb  ldc.i4.0
0x6b5ec  ble      loc_6B6B8
0x6b5f1  ldloc.3
0x6b5f2  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::get_DefaultKeywordsTermStore()
0x6b5f7  brfalse  loc_6B6B8
0x6b5fc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject>::.ctor()
0x6b601  stloc.s  0xD
0x6b603  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::.ctor()
0x6b608  stloc.s  0xE
0x6b60a  ldloc.s  0xE
0x6b60c  ldarg.0
0x6b60d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::set_DefaultLabel(string value)
0x6b612  ldloc.s  0xE
0x6b614  ldarg.1
0x6b615  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::set_Lcid(int32 value)
0x6b61a  ldloc.s  0xE
0x6b61c  ldc.i4.0
0x6b61d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::set_IsSynonym(bool value)
0x6b622  ldloc.s  0xE
0x6b624  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::get_Starts()
0x6b629  ldsfld   string [mscorlib]System.String::Empty
0x6b62e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6b633  ldloc.s  0xE
0x6b635  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::get_Completions()
0x6b63a  ldstr    aCreatenewkeywo// "CreateNewKeyword"
0x6b63f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x6b644  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6b649  ldloc.s  0xE
0x6b64b  ldstr    a22222222222222// "22222222-2222-2222-2222-222222222222"
0x6b650  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::set_Id(string value)
0x6b655  ldloc.s  0xE
0x6b657  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6b65c  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::ApplyPaths(class [mscorlib]System.Collections.Generic.List`1<string> value)
0x6b661  ldloc.s  0xE
0x6b663  ldstr    aCreatenewkeywo_0// "CreateNewKeywordDescription"
0x6b668  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x6b66d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::set_Description(string value)
0x6b672  ldloc.s  0xE
0x6b674  ldsfld   string [mscorlib]System.String::Empty
0x6b679  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject::set_Synonyms(string value)
0x6b67e  ldloc.s  0xD
0x6b680  ldloc.s  0xE
0x6b682  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject>::Add(var<u1>)
0x6b687  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject::.ctor()
0x6b68c  stloc.s  0xF
0x6b68e  ldloc.s  0xF
0x6b690  ldstr    aDisambiguation// "DisambiguationNoneOfAbove"
0x6b695  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x6b69a  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject::set_Header(string value)
0x6b69f  ldloc.s  0xF
0x6b6a1  ldloc.s  0xD
0x6b6a3  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject::ApplySuggestions(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject> value)
0x6b6a8  ldloc.s  0xF
0x6b6aa  ldc.i4.1
0x6b6ab  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject::set_IsNewKeyword(bool value)
0x6b6b0  ldloc.0
0x6b6b1  ldloc.s  0xF
0x6b6b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject>::Add(var<u1>)
0x6b6b8  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionsReturnObject::.ctor()
0x6b6bd  stloc.s  0x10
0x6b6bf  ldloc.s  0x10
0x6b6c1  ldloc.0
0x6b6c2  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.SuggestionsReturnObject::ApplyGroups(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject> value)
0x6b6c7  ldloc.s  0x10
0x6b6c9  ret
```
