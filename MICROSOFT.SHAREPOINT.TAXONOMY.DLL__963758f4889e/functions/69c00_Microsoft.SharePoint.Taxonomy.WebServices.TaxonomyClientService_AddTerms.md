# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::AddTerms

- ea: `0x69c00`
- end: `0x69fa5`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::AddTerms`
- size: `933`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x2acd0`
- `0x48810`
- `0x4bad0`
- `0x4cb30`
- `0x4cc10`
- `0x4d190`
- `0x505d0`
- `0x50680`
- `0x52f00`
- `0x53f80`
- `0x54710`
- `0x55050`
- `0x55440`
- `0x55770`
- `0x557e0`
- `0x69c00`

## string_xrefs

- `0x69c0c`: `TaxonomyClientService: Add terms started`
- `0x69f6f`: `TaxonomyClientService: Add terms failed: {0}`
- `0x69f97`: `TaxonomyClientService: Add terms finished`

## pseudocode

```c

```

## disassembly

```asm
0x69c00  ldc.i4   0x66363831
0x69c05  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x69c0a  ldc.i4.s 0x64
0x69c0c  ldstr    aTaxonomyclient_6// "TaxonomyClientService: Add terms starte"...
0x69c11  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x69c16  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x69c1b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x69c20  stloc.0
0x69c21  ldloc.0
0x69c22  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x69c27  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::EnsureAuthentication(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x69c2c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x69c31  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x69c36  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x69c3b  stloc.1
0x69c3c  ldloc.1
0x69c3d  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x69c42  brtrue.s loc_69C50
0x69c44  ldsfld   string [mscorlib]System.String::Empty
0x69c49  stloc.s  0x17
0x69c4b  leave    loc_69FA2
0x69c50  ldloc.0
0x69c51  ldc.i4.1
0x69c52  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, bool updateCache)
0x69c57  stloc.2
0x69c58  ldarg.2
0x69c59  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69c5e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69c63  brfalse.s loc_69C6E
0x69c65  ldloc.2
0x69c66  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::get_DefaultKeywordsTermStore()
0x69c6b  stloc.3
0x69c6c  br.s     loc_69C7B
0x69c6e  ldloc.2
0x69c6f  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x69c74  ldarg.1
0x69c75  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.IndexedCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Item(!!T0)
0x69c7a  stloc.3
0x69c7b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::.ctor()
0x69c80  stloc.s  4
0x69c82  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x69c87  stloc.s  5
0x69c89  ldloc.3
0x69c8a  brfalse  loc_69F4C
0x69c8f  ldarg.2
0x69c90  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69c95  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69c9a  brfalse.s loc_69CA9
0x69c9c  ldloc.3
0x69c9d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::get_KeywordsTermSet()
0x69ca2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x69ca7  starg.s  2
0x69ca9  ldloc.3
0x69caa  ldarg.2
0x69cab  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x69cb0  stloc.s  6
0x69cb2  ldloc.s  6
0x69cb4  callvirt instance bool Microsoft.SharePoint.Taxonomy.TermSet::get_IsOpenForTermCreation()
0x69cb9  brtrue.s loc_69CC7
0x69cbb  ldsfld   string [mscorlib]System.String::Empty
0x69cc0  stloc.s  0x17
0x69cc2  leave    loc_69FA2
0x69cc7  ldarg.s  4
0x69cc9  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x69cce  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x69cd3  stloc.s  7
0x69cd5  ldloc.s  7
0x69cd7  ldc.i4.0
0x69cd8  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x69cdd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::.ctor()
0x69ce2  stloc.s  8
0x69ce4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x69ce9  stloc.s  9
0x69ceb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::.ctor()
0x69cf0  stloc.s  0xA
0x69cf2  ldloc.3
0x69cf3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.SharePoint.Taxonomy.TermStore::get_Languages()
0x69cf8  ldarg.3
0x69cf9  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x69cfe  brtrue.s loc_69D08
0x69d00  ldloc.3
0x69d01  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x69d06  starg.s  3
0x69d08  ldloc.s  7
0x69d0a  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x69d0f  brfalse  loc_69EF6
0x69d14  ldloc.s  7
0x69d16  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x69d1b  brfalse  loc_69EF6
0x69d20  ldloc.s  7
0x69d22  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x69d27  ldstr    aNewterms// "newTerms"
0x69d2c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x69d31  brfalse  loc_69EF6
0x69d36  ldnull
0x69d37  stloc.s  0xB
0x69d39  ldc.i4.0
0x69d3a  stloc.s  0xC
0x69d3c  br       loc_69ED7
0x69d41  ldc.i4.0
0x69d42  stloc.s  0xD
0x69d44  br.s     loc_69D54
0x69d46  ldloc.s  7
0x69d48  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x69d4d  brtrue.s loc_69D54
0x69d4f  ldc.i4.1
0x69d50  stloc.s  0xD
0x69d52  br.s     loc_69D5D
0x69d54  ldloc.s  7
0x69d56  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x69d5b  brfalse.s loc_69D46
0x69d5d  ldloc.s  0xD
0x69d5f  brtrue   loc_69EF6
0x69d64  ldloc.s  7
0x69d66  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x69d6b  ldloc.s  0xC
0x69d6d  bge.s    loc_69D98
0x69d6f  ldc.i4.0
0x69d70  stloc.s  0xE
0x69d72  br.s     loc_69D8A
0x69d74  ldloc.s  0xA
0x69d76  ldloc.s  0xA
0x69d78  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x69d7d  ldc.i4.1
0x69d7e  sub.ovf
0x69d7f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::RemoveAt(int32)
0x69d84  ldloc.s  0xE
0x69d86  ldc.i4.1
0x69d87  add.ovf
0x69d88  stloc.s  0xE
0x69d8a  ldloc.s  0xE
0x69d8c  ldloc.s  0xC
0x69d8e  ldloc.s  7
0x69d90  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x69d95  sub.ovf
0x69d96  blt.s    loc_69D74
0x69d98  ldloc.s  7
0x69d9a  ldstr    aLabel_0// "label"
0x69d9f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x69da4  stloc.s  0xF
0x69da6  ldloc.s  7
0x69da8  ldstr    aClientid_0// "clientId"
0x69dad  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x69db2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69db7  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x69dbc  stloc.s  0x10
0x69dbe  ldloc.s  0xB
0x69dc0  brfalse.s loc_69E04
0x69dc2  ldloc.s  7
0x69dc4  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x69dc9  ldloc.s  0xC
0x69dcb  ble.s    loc_69E04
0x69dcd  ldarg.2
0x69dce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69dd3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69dd8  brfalse.s loc_69DEA
0x69dda  ldstr    aErrorkeywordte// "ErrorKeywordTermSetNoHierarchy"
0x69ddf  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x69de4  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x69de9  throw
0x69dea  ldloc.s  0xA
0x69dec  ldloc.s  0xB
0x69dee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::Add(var<u1>)
0x69df3  ldloc.s  0xB
0x69df5  ldloc.s  0xF
0x69df7  ldarg.3
0x69df8  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm(string name, int32 lcid)
0x69dfd  stloc.s  0xB
0x69dff  br       loc_69EB4
0x69e04  ldloc.s  0xA
0x69e06  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x69e0b  ldc.i4.0
0x69e0c  ble.s    loc_69E2D
0x69e0e  ldloc.s  0xA
0x69e10  ldloc.s  0xA
0x69e12  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x69e17  ldc.i4.1
0x69e18  sub.ovf
0x69e19  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x69e1e  ldloc.s  0xF
0x69e20  ldarg.3
0x69e21  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm(string name, int32 lcid)
0x69e26  stloc.s  0xB
0x69e28  br       loc_69EB4
0x69e2d  ldloca.s 0x11
0x69e2f  ldloc.s  7
0x69e31  ldstr    aParenttermid_1// "parentTermId"
0x69e36  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x69e3b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x69e40  ldarg.2
0x69e41  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69e46  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69e4b  brfalse.s loc_69E6B
0x69e4d  ldloc.s  0x11
0x69e4f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69e54  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69e59  brfalse.s loc_69E6B
0x69e5b  ldstr    aErrorkeywordte// "ErrorKeywordTermSetNoHierarchy"
0x69e60  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x69e65  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x69e6a  throw
0x69e6b  ldnull
0x69e6c  stloc.s  0x12
0x69e6e  ldnull
0x69e6f  stloc.s  0x13
0x69e71  ldloc.s  0x11
0x69e73  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69e78  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69e7d  brfalse.s loc_69E90
0x69e7f  ldloc.3
0x69e80  ldarg.2
0x69e81  ldloc.s  0x11
0x69e83  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x69e88  stloc.s  0x13
0x69e8a  ldloc.s  0x13
0x69e8c  stloc.s  0x12
0x69e8e  br.s     loc_69E94
0x69e90  ldloc.s  6
0x69e92  stloc.s  0x12
0x69e94  ldloc.s  0x12
0x69e96  brtrue.s loc_69EA8
0x69e98  ldstr    aErrorparentnot// "ErrorParentNotFound"
0x69e9d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x69ea2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x69ea7  throw
0x69ea8  ldloc.s  0x12
0x69eaa  ldloc.s  0xF
0x69eac  ldarg.3
0x69ead  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm(string name, int32 lcid)
0x69eb2  stloc.s  0xB
0x69eb4  ldloc.s  8
0x69eb6  ldloc.s  0xB
0x69eb8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::Add(var<u1>)
0x69ebd  ldloc.s  9
0x69ebf  ldloc.s  0x10
0x69ec1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x69ec6  ldloc.s  5
0x69ec8  ldloc.3
0x69ec9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>)
0x69ece  ldloc.s  7
0x69ed0  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x69ed5  stloc.s  0xC
0x69ed7  ldloc.s  7
0x69ed9  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x69ede  brfalse.s loc_69EF6
0x69ee0  ldloc.s  7
0x69ee2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x69ee7  ldstr    aNewterm// "newTerm"
0x69eec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x69ef1  brtrue   loc_69D41
0x69ef6  ldloc.3
0x69ef7  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x69efc  ldc.i4.0
0x69efd  stloc.s  0x14
0x69eff  br.s     loc_69F33
0x69f01  ldloc.s  8
0x69f03  ldloc.s  0x14
0x69f05  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x69f0a  ldloc.s  9
0x69f0c  ldloc.s  0x14
0x69f0e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0x69f13  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::set_ClientId(int32 value)
0x69f18  ldloc.s  4
0x69f1a  ldloc.s  8
0x69f1c  ldloc.s  0x14
0x69f1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x69f23  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x69f28  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::Add(var<u1>)
0x69f2d  ldloc.s  0x14
0x69f2f  ldc.i4.1
0x69f30  add.ovf
0x69f31  stloc.s  0x14
0x69f33  ldloc.s  0x14
0x69f35  ldloc.s  8
0x69f37  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x69f3c  blt.s    loc_69F01
0x69f3e  leave.s  loc_69F4C
0x69f40  ldloc.s  7
0x69f42  brfalse.s loc_69F4B
0x69f44  ldloc.s  7
0x69f46  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69f4b  endfinally
0x69f4c  ldloc.s  5
0x69f4e  ldloc.s  4
0x69f50  ldarg.3
0x69f51  ldc.i4.0
0x69f52  ldnull
0x69f53  ldnull
0x69f54  call     T0x2B0000AC
0x69f59  stloc.s  0x15
0x69f5b  ldloc.s  0x15
0x69f5d  stloc.s  0x17
0x69f5f  leave.s  loc_69FA2
0x69f61  stloc.s  0x16
0x69f63  ldc.i4   0x66363833
0x69f68  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x69f6d  ldc.i4.s 0xA
0x69f6f  ldstr    aTaxonomyclient_7// "TaxonomyClientService: Add terms failed"...
0x69f74  ldc.i4.1
0x69f75  newarr   [mscorlib]System.Object
  ... truncated ...
```
