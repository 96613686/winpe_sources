# Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::SetCanToggleHidden

- ea: `0x251d0`
- end: `0x25472`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::SetCanToggleHidden`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x3f5d0`

## callees

- `0x251d0`

## string_xrefs

- `0x25272`: `XmlDocument.LoadXml threw.  Removing control characters.  Exception: `
- `0x253a7`: `TaxonomyFeatureReceiver.SetCanToggleHidden: field = {0} ({1}), canToggleHidden is already = {2}.  No update required.`

## pseudocode

```c

```

## disassembly

```asm
0x251d0  ldc.i4   0x24E59C
0x251d5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x251da  ldc.i4.s 0x64
0x251dc  ldstr    aBeginTaxonomyf// "Begin TaxonomyFeatureReceiver.SetCanTog"...
0x251e1  ldc.i4.3
0x251e2  newarr   [mscorlib]System.Object
0x251e7  stloc.s  0xD
0x251e9  ldloc.s  0xD
0x251eb  ldc.i4.0
0x251ec  ldarg.0
0x251ed  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Title()
0x251f2  stelem.ref
0x251f3  ldloc.s  0xD
0x251f5  ldc.i4.1
0x251f6  ldarg.0
0x251f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Id()
0x251fc  stloc.s  0xE
0x251fe  ldloca.s 0xE
0x25200  constrained. [mscorlib]System.Guid
0x25206  callvirt instance string [mscorlib]System.Object::ToString()
0x2520b  stelem.ref
0x2520c  ldloc.s  0xD
0x2520e  ldc.i4.2
0x2520f  ldarg.1
0x25210  box      [mscorlib]System.Boolean
0x25215  stelem.ref
0x25216  ldloc.s  0xD
0x25218  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2521d  ldarg.0
0x2521e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_SchemaXml()
0x25223  stloc.0
0x25224  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x25229  stloc.1
0x2522a  ldnull
0x2522b  stloc.2
0x2522c  ldloc.0
0x2522d  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x25232  stloc.2
0x25233  ldloc.2
0x25234  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x25239  stloc.3
0x2523a  ldnull
0x2523b  stloc.2
0x2523c  ldloc.3
0x2523d  ldc.i4.0
0x2523e  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x25243  ldloc.1
0x25244  ldloc.3
0x25245  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x2524a  leave.s  loc_25256
0x2524c  ldloc.3
0x2524d  brfalse.s loc_25255
0x2524f  ldloc.3
0x25250  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25255  endfinally
0x25256  leave.s  loc_25262
0x25258  ldloc.2
0x25259  brfalse.s loc_25261
0x2525b  ldloc.2
0x2525c  callvirt instance void [mscorlib]System.IO.TextReader::Dispose()
0x25261  endfinally
0x25262  leave.s  loc_252D2
0x25264  stloc.s  4
0x25266  ldc.i4   0x24E59D
0x2526b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x25270  ldc.i4.s 0x64
0x25272  ldstr    aXmldocumentLoa// "XmlDocument.LoadXml threw.  Removing co"...
0x25277  ldloc.s  4
0x25279  callvirt instance string [mscorlib]System.Object::ToString()
0x2527e  call     string [mscorlib]System.String::Concat(string, string)
0x25283  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x25288  ldnull
0x25289  stloc.s  5
0x2528b  ldloc.0
0x2528c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPStringUtility::RemoveControlChars(string)
0x25291  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x25296  stloc.s  5
0x25298  ldloc.s  5
0x2529a  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x2529f  stloc.s  6
0x252a1  ldnull
0x252a2  stloc.s  5
0x252a4  ldloc.s  6
0x252a6  ldc.i4.0
0x252a7  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x252ac  ldloc.1
0x252ad  ldloc.s  6
0x252af  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x252b4  leave.s  loc_252C2
0x252b6  ldloc.s  6
0x252b8  brfalse.s loc_252C1
0x252ba  ldloc.s  6
0x252bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x252c1  endfinally
0x252c2  leave.s  loc_252D0
0x252c4  ldloc.s  5
0x252c6  brfalse.s loc_252CF
0x252c8  ldloc.s  5
0x252ca  callvirt instance void [mscorlib]System.IO.TextReader::Dispose()
0x252cf  endfinally
0x252d0  leave.s  loc_252D2
0x252d2  ldloc.1
0x252d3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x252d8  stloc.s  7
0x252da  ldloc.s  7
0x252dc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x252e1  stloc.s  8
0x252e3  ldloc.s  8
0x252e5  ldstr    aCantogglehidde// "CanToggleHidden"
0x252ea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x252ef  stloc.s  9
0x252f1  ldc.i4.0
0x252f2  stloc.s  0xA
0x252f4  ldloc.s  9
0x252f6  brtrue.s loc_25343
0x252f8  ldc.i4   0x24E59E
0x252fd  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x25302  ldc.i4.s 0x64
0x25304  ldstr    aTaxonomyfeatur// "TaxonomyFeatureReceiver.SetCanToggleHid"...
0x25309  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2530e  ldloc.1
0x2530f  ldstr    aCantogglehidde// "CanToggleHidden"
0x25314  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x25319  stloc.s  0xB
0x2531b  ldloc.s  0xB
0x2531d  ldarg.1
0x2531e  brtrue.s loc_25327
0x25320  ldstr    aFalse_1// "FALSE"
0x25325  br.s     loc_2532C
0x25327  ldstr    aTrue_1// "TRUE"
0x2532c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x25331  ldloc.s  8
0x25333  ldloc.s  0xB
0x25335  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x2533a  pop
0x2533b  ldc.i4.1
0x2533c  stloc.s  0xA
0x2533e  br       loc_253E8
0x25343  ldarg.0
0x25344  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_CanToggleHidden()
0x25349  stloc.s  0xF
0x2534b  ldloca.s 0xF
0x2534d  ldarg.1
0x2534e  call     instance bool [mscorlib]System.Boolean::Equals(bool)
0x25353  brtrue.s loc_2539B
0x25355  ldc.i4   0x24E59F
0x2535a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2535f  ldc.i4.s 0x64
0x25361  ldstr    aTaxonomyfeatur_0// "TaxonomyFeatureReceiver.SetCanToggleHid"...
0x25366  ldc.i4.1
0x25367  newarr   [mscorlib]System.Object
0x2536c  stloc.s  0x10
0x2536e  ldloc.s  0x10
0x25370  ldc.i4.0
0x25371  ldloc.s  9
0x25373  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x25378  stelem.ref
0x25379  ldloc.s  0x10
0x2537b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x25380  ldloc.s  9
0x25382  ldarg.1
0x25383  brtrue.s loc_2538C
0x25385  ldstr    aFalse_1// "FALSE"
0x2538a  br.s     loc_25391
0x2538c  ldstr    aTrue_1// "TRUE"
0x25391  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x25396  ldc.i4.1
0x25397  stloc.s  0xA
0x25399  br.s     loc_253E8
0x2539b  ldc.i4   0x24E5A0
0x253a0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x253a5  ldc.i4.s 0x64
0x253a7  ldstr    aTaxonomyfeatur_1// "TaxonomyFeatureReceiver.SetCanToggleHid"...
0x253ac  ldc.i4.3
0x253ad  newarr   [mscorlib]System.Object
0x253b2  stloc.s  0x11
0x253b4  ldloc.s  0x11
0x253b6  ldc.i4.0
0x253b7  ldarg.0
0x253b8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Title()
0x253bd  stelem.ref
0x253be  ldloc.s  0x11
0x253c0  ldc.i4.1
0x253c1  ldarg.0
0x253c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Id()
0x253c7  stloc.s  0x12
0x253c9  ldloca.s 0x12
0x253cb  constrained. [mscorlib]System.Guid
0x253d1  callvirt instance string [mscorlib]System.Object::ToString()
0x253d6  stelem.ref
0x253d7  ldloc.s  0x11
0x253d9  ldc.i4.2
0x253da  ldarg.1
0x253db  box      [mscorlib]System.Boolean
0x253e0  stelem.ref
0x253e1  ldloc.s  0x11
0x253e3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x253e8  ldloc.s  0xA
0x253ea  brfalse.s loc_25424
0x253ec  ldarg.0
0x253ed  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Sealed()
0x253f2  stloc.s  0xC
0x253f4  ldarg.0
0x253f5  ldc.i4.1
0x253f6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_PushChangesToLists(bool)
0x253fb  ldloc.s  0xC
0x253fd  brfalse.s loc_25406
0x253ff  ldarg.0
0x25400  ldc.i4.0
0x25401  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Sealed(bool)
0x25406  ldarg.0
0x25407  ldloc.1
0x25408  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x2540d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_SchemaXml(string)
0x25412  ldarg.0
0x25413  ldc.i4.1
0x25414  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::Update(bool)
0x25419  ldloc.s  0xC
0x2541b  brfalse.s loc_25424
0x2541d  ldarg.0
0x2541e  ldc.i4.1
0x2541f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Sealed(bool)
0x25424  ldc.i4   0x24E5A1
0x25429  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2542e  ldc.i4.s 0x64
0x25430  ldstr    aEndTaxonomyfea// "End TaxonomyFeatureReceiver.SetCanToggl"...
0x25435  ldc.i4.3
0x25436  newarr   [mscorlib]System.Object
0x2543b  stloc.s  0x13
0x2543d  ldloc.s  0x13
0x2543f  ldc.i4.0
0x25440  ldarg.0
0x25441  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Title()
0x25446  stelem.ref
0x25447  ldloc.s  0x13
0x25449  ldc.i4.1
0x2544a  ldarg.0
0x2544b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Id()
0x25450  stloc.s  0x14
0x25452  ldloca.s 0x14
0x25454  constrained. [mscorlib]System.Guid
0x2545a  callvirt instance string [mscorlib]System.Object::ToString()
0x2545f  stelem.ref
0x25460  ldloc.s  0x13
0x25462  ldc.i4.2
0x25463  ldarg.1
0x25464  box      [mscorlib]System.Boolean
0x25469  stelem.ref
0x2546a  ldloc.s  0x13
0x2546c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x25471  ret
```
