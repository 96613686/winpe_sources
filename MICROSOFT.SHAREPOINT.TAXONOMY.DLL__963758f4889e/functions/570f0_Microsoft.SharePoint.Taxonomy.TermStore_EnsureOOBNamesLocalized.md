# Microsoft.SharePoint.Taxonomy.TermStore::EnsureOOBNamesLocalized

- ea: `0x570f0`
- end: `0x571d6`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::EnsureOOBNamesLocalized`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x53de0`

## callees

- `0x2acf0`
- `0x53090`
- `0x55770`
- `0x55830`
- `0x570f0`
- `0x571e0`
- `0x57200`

## string_xrefs

- `0x5713a`: `CompanyInclusionsTermSetName`
- `0x57151`: `CompanyExclusionsTermSetName`

## pseudocode

```c

```

## disassembly

```asm
0x570f0  ldstr    aKeywordstermse// "KeywordsTermSetName"
0x570f5  ldarg.1
0x570f6  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x570fb  stloc.0
0x570fc  ldstr    aOrphanedtermst// "OrphanedTermsTermSetName"
0x57101  ldarg.1
0x57102  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x57107  stloc.1
0x57108  ldloc.0
0x57109  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5710e  brtrue.s loc_5711E
0x57110  ldarg.0
0x57111  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::get_KeywordsTermSet()
0x57116  ldloc.0
0x57117  ldarg.1
0x57118  ldc.i4.0
0x57119  callvirt instance void Microsoft.SharePoint.Taxonomy.TermSet::SetName(string value, int32 lcid, bool checkSecurity)
0x5711e  ldloc.1
0x5711f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57124  brtrue.s loc_57134
0x57126  ldarg.0
0x57127  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::get_OrphanedTermsTermSet()
0x5712c  ldloc.1
0x5712d  ldarg.1
0x5712e  ldc.i4.0
0x5712f  callvirt instance void Microsoft.SharePoint.Taxonomy.TermSet::SetName(string value, int32 lcid, bool checkSecurity)
0x57134  ldarg.0
0x57135  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::SearchDictionaryTermSetGuidCompanyInclusions
0x5713a  ldstr    aCompanyinclusi// "CompanyInclusionsTermSetName"
0x5713f  ldarg.1
0x57140  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x57145  ldarg.1
0x57146  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::LocalizeOOBSearchDictionaryTermSet(valuetype [mscorlib]System.Guid termSetId, string localizedName, int32 lcid)
0x5714b  ldarg.0
0x5714c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::SearchDictionaryTermSetGuidCompanyExclusions
0x57151  ldstr    aCompanyexclusi// "CompanyExclusionsTermSetName"
0x57156  ldarg.1
0x57157  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x5715c  ldarg.1
0x5715d  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::LocalizeOOBSearchDictionaryTermSet(valuetype [mscorlib]System.Guid termSetId, string localizedName, int32 lcid)
0x57162  ldarg.0
0x57163  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::SearchDictionaryTermSetGuidQuerySpellCheckInclusions
0x57168  ldstr    aQueryspellingi// "QuerySpellingInclusionsTermSetName"
0x5716d  ldarg.1
0x5716e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x57173  ldarg.1
0x57174  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::LocalizeOOBSearchDictionaryTermSet(valuetype [mscorlib]System.Guid termSetId, string localizedName, int32 lcid)
0x57179  ldarg.0
0x5717a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::SearchDictionaryTermSetGuidQuerySpellCheckExclusions
0x5717f  ldstr    aQueryspellinge// "QuerySpellingExclusionsTermSetName"
0x57184  ldarg.1
0x57185  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x5718a  ldarg.1
0x5718b  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::LocalizeOOBSearchDictionaryTermSet(valuetype [mscorlib]System.Guid termSetId, string localizedName, int32 lcid)
0x57190  ldarg.0
0x57191  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::GlobalSearchPeopleTermSetGUID_JobTitle
0x57196  ldstr    aTermsetsJobtit// "TermSets_JobTitle"
0x5719b  ldarg.1
0x5719c  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x571a1  ldarg.1
0x571a2  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::LocalizeOOBPeopleTermSets(valuetype [mscorlib]System.Guid termSetId, string localizedName, int32 lcid)
0x571a7  ldarg.0
0x571a8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::GlobalSearchPeopleTermSetGUID_Department
0x571ad  ldstr    aTermsetsDepart// "TermSets_Department"
0x571b2  ldarg.1
0x571b3  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x571b8  ldarg.1
0x571b9  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::LocalizeOOBPeopleTermSets(valuetype [mscorlib]System.Guid termSetId, string localizedName, int32 lcid)
0x571be  ldarg.0
0x571bf  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::GlobalSearchPeopleTermSetGUID_Location
0x571c4  ldstr    aTermsetsLocati// "TermSets_Location"
0x571c9  ldarg.1
0x571ca  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName, int32 lcid)
0x571cf  ldarg.1
0x571d0  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::LocalizeOOBPeopleTermSets(valuetype [mscorlib]System.Guid termSetId, string localizedName, int32 lcid)
0x571d5  ret
```
