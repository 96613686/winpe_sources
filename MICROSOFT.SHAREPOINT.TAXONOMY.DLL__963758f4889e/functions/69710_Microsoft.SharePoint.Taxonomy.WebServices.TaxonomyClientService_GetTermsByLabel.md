# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetTermsByLabel

- ea: `0x69710`
- end: `0x69bf1`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetTermsByLabel`
- size: `1249`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x242d0`
- `0x24910`
- `0x2ecb0`
- `0x2f970`
- `0x313d0`
- `0x48810`
- `0x4baa0`
- `0x4cb30`
- `0x4cc10`
- `0x4d190`
- `0x50680`
- `0x53f80`
- `0x546d0`
- `0x55440`
- `0x55770`
- `0x557e0`
- `0x56bd0`
- `0x69710`
- `0x6b460`
- `0x713d0`
- `0x71990`

## string_xrefs

- `0x6971c`: `TaxonomyClientService: Get terms by label started`
- `0x69bbb`: `TaxonomyClientService: Get terms by label failed: {0}`
- `0x69be3`: `TaxonomyClientService: Get terms by label finished`

## pseudocode

```c

```

## disassembly

```asm
0x69710  ldc.i4   0x66363779
0x69715  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6971a  ldc.i4.s 0x64
0x6971c  ldstr    aTaxonomyclient_3// "TaxonomyClientService: Get terms by lab"...
0x69721  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x69726  ldarg.1
0x69727  ldstr    aLabel_0// "label"
0x6972c  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNullOrEmpty(string value, string parameterName)
0x69731  ldarg.3
0x69732  brtrue   loc_69958
0x69737  ldnull
0x69738  stloc.0
0x69739  ldarg.1
0x6973a  ldarg.2
0x6973b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69740  stloc.s  0x22
0x69742  ldloca.s 0x22
0x69744  constrained. [mscorlib]System.Guid
0x6974a  callvirt instance string [mscorlib]System.Object::ToString()
0x6974f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69754  stloc.s  0x23
0x69756  ldloca.s 0x23
0x69758  constrained. [mscorlib]System.Guid
0x6975e  callvirt instance string [mscorlib]System.Object::ToString()
0x69763  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69768  ldc.i4.1
0x69769  ldc.i4.1
0x6976a  ldc.i4.0
0x6976b  ldc.i4.0
0x6976c  ldc.i4.0
0x6976d  ldc.i4.0
0x6976e  ldc.i4.0
0x6976f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69774  call     class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionsReturnObject Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetSuggestionsInternal(string start, int32 lcid, string sspList, string termSetList, valuetype [mscorlib]System.Guid anchorId, bool isSpanTermStores, bool isSpanTermSets, bool isIncludeUnavailable, bool isIncludeDeprecated, bool isAddTerms, bool isIncludePathData, bool excludeKeyword, valuetype [mscorlib]System.Guid excludedTermset)
0x69779  stloc.1
0x6977a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6977f  stloc.2
0x69780  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x69785  stloc.3
0x69786  ldloc.3
0x69787  ldc.i4.0
0x69788  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x6978d  ldloc.2
0x6978e  ldloc.3
0x6978f  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x69794  stloc.s  4
0x69796  ldloc.s  4
0x69798  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartDocument()
0x6979d  ldloc.s  4
0x6979f  ldstr    aTermstore// "TermStore"
0x697a4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x697a9  ldloc.1
0x697aa  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject> Microsoft.SharePoint.Taxonomy.WebServices.SuggestionsReturnObject::get_Groups()
0x697af  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject>::GetEnumerator()
0x697b4  stloc.s  0x24
0x697b6  br.s     loc_697FC
0x697b8  ldloca.s 0x24
0x697ba  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject>::get_Current()
0x697bf  stloc.s  5
0x697c1  ldloc.s  5
0x697c3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject> Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject::get_Suggestions()
0x697c8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject>::GetEnumerator()
0x697cd  stloc.s  0x25
0x697cf  br.s     loc_697E3
0x697d1  ldloca.s 0x25
0x697d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject>::get_Current()
0x697d8  stloc.s  6
0x697da  ldloc.s  4
0x697dc  ldloc.s  6
0x697de  call     void Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::SerializeToExternalFormat(class [System.Xml]System.Xml.XmlWriter writer, class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject suggestion)
0x697e3  ldloca.s 0x25
0x697e5  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject>::MoveNext()
0x697ea  brtrue.s loc_697D1
0x697ec  leave.s  loc_697FC
0x697ee  ldloca.s 0x25
0x697f0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionReturnObject>
0x697f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x697fb  endfinally
0x697fc  ldloca.s 0x24
0x697fe  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject>::MoveNext()
0x69803  brtrue.s loc_697B8
0x69805  leave.s  loc_69815
0x69807  ldloca.s 0x24
0x69809  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.WebServices.SuggestionGroupReturnObject>
0x6980f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69814  endfinally
0x69815  ldarg.s  5
0x69817  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6981c  brtrue   loc_6992D
0x69821  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x69826  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6982b  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x69830  stloc.s  7
0x69832  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x69837  stloc.s  8
0x69839  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x6983e  pop
0x6983f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::.ctor()
0x69844  stloc.s  9
0x69846  ldnull
0x69847  stloc.s  0xA
0x69849  ldnull
0x6984a  stloc.s  0xB
0x6984c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x69851  stloc.s  0xA
0x69853  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x69858  stloc.s  0xB
0x6985a  ldloc.s  7
0x6985c  ldloc.s  8
0x6985e  ldloc.s  9
0x69860  ldarg.s  5
0x69862  ldloc.s  0xA
0x69864  ldloc.s  0xB
0x69866  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetValidatedTermIds(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore> termStores, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm> sharedTerms, string termIds, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> validatedGuids, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> invalidGuids)
0x6986b  ldloc.s  0xA
0x6986d  brfalse.s loc_698CC
0x6986f  ldloc.s  0xA
0x69871  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x69876  ldc.i4.0
0x69877  ble.s    loc_698CC
0x69879  ldloc.s  0xA
0x6987b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x69880  stloc.s  0x26
0x69882  br.s     loc_698B3
0x69884  ldloca.s 0x26
0x69886  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x6988b  stloc.s  0xC
0x6988d  ldloc.s  4
0x6988f  ldstr    aVi// "VI"
0x69894  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x69899  ldloc.s  4
0x6989b  ldstr    aA9// "a9"
0x698a0  ldloc.s  0xC
0x698a2  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x698a7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x698ac  ldloc.s  4
0x698ae  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x698b3  ldloca.s 0x26
0x698b5  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x698ba  brtrue.s loc_69884
0x698bc  leave.s  loc_698CC
0x698be  ldloca.s 0x26
0x698c0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x698c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x698cb  endfinally
0x698cc  ldloc.s  0xB
0x698ce  brfalse.s loc_6992D
0x698d0  ldloc.s  0xB
0x698d2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x698d7  ldc.i4.0
0x698d8  ble.s    loc_6992D
0x698da  ldloc.s  0xB
0x698dc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x698e1  stloc.s  0x27
0x698e3  br.s     loc_69914
0x698e5  ldloca.s 0x27
0x698e7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x698ec  stloc.s  0xD
0x698ee  ldloc.s  4
0x698f0  ldstr    aIi// "II"
0x698f5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x698fa  ldloc.s  4
0x698fc  ldstr    aA9// "a9"
0x69901  ldloc.s  0xD
0x69903  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x69908  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x6990d  ldloc.s  4
0x6990f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x69914  ldloca.s 0x27
0x69916  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x6991b  brtrue.s loc_698E5
0x6991d  leave.s  loc_6992D
0x6991f  ldloca.s 0x27
0x69921  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x69927  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6992c  endfinally
0x6992d  ldloc.s  4
0x6992f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x69934  ldloc.s  4
0x69936  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x6993b  ldloc.2
0x6993c  callvirt instance string [mscorlib]System.Object::ToString()
0x69941  stloc.0
0x69942  leave.s  loc_69950
0x69944  ldloc.s  4
0x69946  brfalse.s loc_6994F
0x69948  ldloc.s  4
0x6994a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6994f  endfinally
0x69950  ldloc.0
0x69951  stloc.s  0x21
0x69953  leave    loc_69BEE
0x69958  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6995d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x69962  stloc.s  0xE
0x69964  ldloc.s  0xE
0x69966  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x6996b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::EnsureAuthentication(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x69970  ldloc.s  0xE
0x69972  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x69977  stloc.s  0xF
0x69979  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x6997e  stloc.s  0x10
0x69980  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x69985  stloc.s  0x11
0x69987  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::.ctor()
0x6998c  stloc.s  0x12
0x6998e  ldc.i4.0
0x6998f  stloc.s  0x13
0x69991  ldc.i4.0
0x69992  stloc.s  0x14
0x69994  ldarg.1
0x69995  ldc.i4.1
0x69996  newarr   [mscorlib]System.Char
0x6999b  stloc.s  0x28
0x6999d  ldloc.s  0x28
0x6999f  ldc.i4.0
0x699a0  ldc.i4.s 0x3B
0x699a2  stelem.i2
0x699a3  ldloc.s  0x28
0x699a5  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x699aa  stloc.s  0x15
0x699ac  ldloc.s  0x15
0x699ae  stloc.s  0x29
0x699b0  ldc.i4.0
0x699b1  stloc.s  0x2A
0x699b3  br       loc_69B01
0x699b8  ldloc.s  0x29
0x699ba  ldloc.s  0x2A
0x699bc  ldelem.ref
0x699bd  stloc.s  0x16
0x699bf  ldloc.s  0xF
0x699c1  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x699c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::GetEnumerator()
0x699cb  stloc.s  0x2B
0x699cd  br       loc_69A7D
0x699d2  ldloc.s  0x2B
0x699d4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Current()
0x699d9  stloc.s  0x17
0x699db  ldloc.s  0x17
0x699dd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.SharePoint.Taxonomy.TermStore::get_Languages()
0x699e2  ldarg.2
0x699e3  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x699e8  brtrue.s loc_699F3
0x699ea  ldloc.s  0x17
0x699ec  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x699f1  starg.s  2
0x699f3  ldloc.s  0x17
0x699f5  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x699fa  ldloca.s 0x2C
0x699fc  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x69a02  ldloc.s  0x2C
0x69a04  ldloca.s 0x2D
0x69a06  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x69a0c  ldloc.s  0x2D
0x69a0e  ldloc.s  0x16
0x69a10  ldarg.2
0x69a11  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x69a16  ldc.i4.0
0x69a17  ldc.i4.0
0x69a18  ldarg.3
0x69a19  ldarg.s  4
0x69a1b  ldc.i4.1
0x69a1c  ldloc.s  0x17
0x69a1e  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x69a23  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x69a28  ldc.i4.1
0x69a29  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm> Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::SearchTermByLabel(valuetype [mscorlib]System.Nullable`1<int32> termSetId, valuetype [mscorlib]System.Nullable`1<int32> anchorId, string label, valuetype [mscorlib]System.Nullable`1<int32> lcid, bool defaultLabelOnly, bool includeIdPath, valuetype Microsoft.SharePoint.Taxonomy.StringMatchOption stringMatchOption, int32 resultCollectionSize, bool getFullPath, valuetype [mscorlib]System.Nullable`1<int32> defaultLcid, bool trimUnavailable)
0x69a2e  stloc.s  0x18
0x69a30  ldloc.s  0x18
0x69a32  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::GetEnumerator()
0x69a37  stloc.s  0x2E
0x69a39  br.s     loc_69A64
0x69a3b  ldloca.s 0x2E
0x69a3d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::get_Current()
0x69a42  stloc.s  0x19
0x69a44  ldloc.s  0x12
0x69a46  ldloc.s  0x19
0x69a48  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::Add(var<u1>)
0x69a4d  ldloc.s  0x11
0x69a4f  ldloc.s  0x19
0x69a51  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_UniqueId()
0x69a56  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x69a5b  ldloc.s  0x10
0x69a5d  ldloc.s  0x17
0x69a5f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>)
0x69a64  ldloca.s 0x2E
0x69a66  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::MoveNext()
0x69a6b  brtrue.s loc_69A3B
0x69a6d  leave.s  loc_69A7D
0x69a6f  ldloca.s 0x2E
0x69a71  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>
0x69a77  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69a7c  endfinally
0x69a7d  ldloc.s  0x2B
0x69a7f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69a84  brtrue   loc_699D2
0x69a89  leave.s  loc_69A97
0x69a8b  ldloc.s  0x2B
0x69a8d  brfalse.s loc_69A96
  ... truncated ...
```
