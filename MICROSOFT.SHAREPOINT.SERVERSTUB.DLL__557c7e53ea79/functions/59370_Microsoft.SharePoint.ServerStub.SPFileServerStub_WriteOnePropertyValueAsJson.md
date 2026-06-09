# Microsoft.SharePoint.ServerStub.SPFileServerStub::WriteOnePropertyValueAsJson

- ea: `0x59370`
- end: `0x5a194`
- name: `Microsoft.SharePoint.ServerStub.SPFileServerStub::WriteOnePropertyValueAsJson`
- size: `3620`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x59370`

## string_xrefs

- `0x594f1`: `ServerRelativePath`
- `0x59e2f`: `ServerRelativePath`
- `0x593cc`: `CheckInComment`
- `0x5975f`: `CheckInComment`
- `0x5946f`: `LinkingUri`
- `0x59b2f`: `LinkingUri`
- `0x5947c`: `LinkingUrl`
- `0x59b79`: `LinkingUrl`
- `0x59518`: `TimeCreated`
- `0x59f0d`: `TimeCreated`

## pseudocode

```c

```

## disassembly

```asm
0x59370  ldc.i4.0
0x59371  stloc.0
0x59372  ldarg.2
0x59373  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x59378  stloc.1
0x59379  ldloc.1
0x5937a  brtrue.s loc_59387
0x5937c  ldstr    aTarget// "target"
0x59381  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x59386  throw
0x59387  ldarg.3
0x59388  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x5938d  dup
0x5938e  stloc.2
0x5938f  brfalse  loc_5A186
0x59394  volatile.
0x59396  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ffb-1
0x5939b  brtrue   loc_59593
0x593a0  ldc.i4.s 0x26
0x593a2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x593a7  dup
0x593a8  ldstr    aActivitycapabi// "ActivityCapabilities"
0x593ad  ldc.i4.0
0x593ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x593b3  dup
0x593b4  ldstr    aAuthor_0// "Author"
0x593b9  ldc.i4.1
0x593ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x593bf  dup
0x593c0  ldstr    aCheckedoutbyus// "CheckedOutByUser"
0x593c5  ldc.i4.2
0x593c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x593cb  dup
0x593cc  ldstr    aCheckincomment_0// "CheckInComment"
0x593d1  ldc.i4.3
0x593d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x593d7  dup
0x593d8  ldstr    aCheckouttype// "CheckOutType"
0x593dd  ldc.i4.4
0x593de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x593e3  dup
0x593e4  ldstr    aClientactiviti_1// "ClientActivities"
0x593e9  ldc.i4.5
0x593ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x593ef  dup
0x593f0  ldstr    aContenttag// "ContentTag"
0x593f5  ldc.i4.6
0x593f6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x593fb  dup
0x593fc  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x59401  ldc.i4.7
0x59402  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59407  dup
0x59408  ldstr    aListid_0// "ListId"
0x5940d  ldc.i4.8
0x5940e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59413  dup
0x59414  ldstr    aEffectiveinfor// "EffectiveInformationRightsManagementSet"...
0x59419  ldc.i4.s 9
0x5941b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59420  dup
0x59421  ldstr    aEtag_0// "ETag"
0x59426  ldc.i4.s 0xA
0x59428  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5942d  dup
0x5942e  ldstr    aExists// "Exists"
0x59433  ldc.i4.s 0xB
0x59435  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5943a  dup
0x5943b  ldstr    aInformationrig// "InformationRightsManagementSettings"
0x59440  ldc.i4.s 0xC
0x59442  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59447  dup
0x59448  ldstr    aIrmenabled// "IrmEnabled"
0x5944d  ldc.i4.s 0xD
0x5944f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59454  dup
0x59455  ldstr    aLength// "Length"
0x5945a  ldc.i4.s 0xE
0x5945c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59461  dup
0x59462  ldstr    aLevel// "Level"
0x59467  ldc.i4.s 0xF
0x59469  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5946e  dup
0x5946f  ldstr    aLinkinguri// "LinkingUri"
0x59474  ldc.i4.s 0x10
0x59476  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5947b  dup
0x5947c  ldstr    aLinkingurl// "LinkingUrl"
0x59481  ldc.i4.s 0x11
0x59483  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59488  dup
0x59489  ldstr    aListitemallfie// "ListItemAllFields"
0x5948e  ldc.i4.s 0x12
0x59490  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59495  dup
0x59496  ldstr    aLockedbyuser// "LockedByUser"
0x5949b  ldc.i4.s 0x13
0x5949d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594a2  dup
0x594a3  ldstr    aMajorversion// "MajorVersion"
0x594a8  ldc.i4.s 0x14
0x594aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594af  dup
0x594b0  ldstr    aMinorversion// "MinorVersion"
0x594b5  ldc.i4.s 0x15
0x594b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594bc  dup
0x594bd  ldstr    aModifiedby// "ModifiedBy"
0x594c2  ldc.i4.s 0x16
0x594c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594c9  dup
0x594ca  ldstr    aName// "Name"
0x594cf  ldc.i4.s 0x17
0x594d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594d6  dup
0x594d7  ldstr    aPagerendertype// "PageRenderType"
0x594dc  ldc.i4.s 0x18
0x594de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594e3  dup
0x594e4  ldstr    aProperties// "Properties"
0x594e9  ldc.i4.s 0x19
0x594eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594f0  dup
0x594f1  ldstr    aServerrelative_0// "ServerRelativePath"
0x594f6  ldc.i4.s 0x1A
0x594f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x594fd  dup
0x594fe  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x59503  ldc.i4.s 0x1B
0x59505  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5950a  dup
0x5950b  ldstr    aSiteid_0// "SiteId"
0x59510  ldc.i4.s 0x1C
0x59512  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59517  dup
0x59518  ldstr    aTimecreated// "TimeCreated"
0x5951d  ldc.i4.s 0x1D
0x5951f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59524  dup
0x59525  ldstr    aTimelastmodifi// "TimeLastModified"
0x5952a  ldc.i4.s 0x1E
0x5952c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59531  dup
0x59532  ldstr    aTitle// "Title"
0x59537  ldc.i4.s 0x1F
0x59539  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5953e  dup
0x5953f  ldstr    aUiversion// "UIVersion"
0x59544  ldc.i4.s 0x20
0x59546  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5954b  dup
0x5954c  ldstr    aUiversionlabel// "UIVersionLabel"
0x59551  ldc.i4.s 0x21
0x59553  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59558  dup
0x59559  ldstr    aUniqueid_0// "UniqueId"
0x5955e  ldc.i4.s 0x22
0x59560  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59565  dup
0x59566  ldstr    aVersionevents// "VersionEvents"
0x5956b  ldc.i4.s 0x23
0x5956d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x59572  dup
0x59573  ldstr    aVersions// "Versions"
0x59578  ldc.i4.s 0x24
0x5957a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5957f  dup
0x59580  ldstr    aWebid_0// "WebId"
0x59585  ldc.i4.s 0x25
0x59587  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5958c  volatile.
0x5958e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ffb-1
0x59593  volatile.
0x59595  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ffb-1
0x5959a  ldloc.2
0x5959b  ldloca.s 3
0x5959d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x595a2  brfalse  loc_5A186
0x595a7  ldloc.3
0x595a8  switch   loc_5964A, loc_59694, loc_596E5, loc_59736, loc_59780, loc_597CA, loc_59814, loc_5985E, loc_598A8, loc_598F2, loc_59943, loc_5998D, loc_599D7, loc_59A28, loc_59A72, loc_59ABC, loc_59B06, loc_59B50, loc_59B9A, loc_59BEB, loc_59C3C, loc_59C86, loc_59CD0, loc_59D21, loc_59D6B, loc_59DB5, loc_59E06, loc_59E50, loc_59E9A, loc_59EE4, loc_59F2E, loc_59F78, loc_59FC2, loc_5A00C, loc_5A056, loc_5A0A0, loc_5A0F1, loc_5A13F
0x59645  br       loc_5A186
0x5964a  ldarg.3
0x5964b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x59650  stloc.s  4
0x59652  ldloca.s 4
0x59654  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x59659  brfalse.s loc_59672
0x5965b  ldarg.3
0x5965c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x59661  stloc.s  5
0x59663  ldloca.s 5
0x59665  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5966a  brtrue.s loc_59672
0x5966c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x59671  throw
0x59672  ldarg.0
0x59673  ldstr    aActivitycapabi// "ActivityCapabilities"
0x59678  ldarg.s  4
0x5967a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5967f  ldc.i4.1
0x59680  stloc.0
0x59681  ldarg.1
0x59682  ldloc.1
0x59683  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityCapabilities [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ActivityCapabilities()
0x59688  ldarg.s  4
0x5968a  call     T0x2B0001B5
0x5968f  br       loc_5A192
0x59694  ldarg.3
0x59695  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5969a  stloc.s  6
0x5969c  ldloca.s 6
0x5969e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x596a3  brfalse.s loc_596BC
0x596a5  ldarg.3
0x596a6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x596ab  stloc.s  7
0x596ad  ldloca.s 7
0x596af  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x596b4  brfalse.s loc_596BC
0x596b6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x596bb  throw
0x596bc  ldarg.0
0x596bd  ldstr    aAuthor_0// "Author"
0x596c2  ldarg.s  4
0x596c4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x596c9  ldc.i4.1
0x596ca  stloc.0
0x596cb  ldarg.0
0x596cc  ldarg.1
0x596cd  ldloc.1
0x596ce  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Author()
0x596d3  ldarg.3
0x596d4  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x596d9  ldarg.s  4
0x596db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x596e0  br       loc_5A192
0x596e5  ldarg.3
0x596e6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x596eb  stloc.s  8
0x596ed  ldloca.s 8
0x596ef  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x596f4  brfalse.s loc_5970D
0x596f6  ldarg.3
0x596f7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x596fc  stloc.s  9
0x596fe  ldloca.s 9
0x59700  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x59705  brfalse.s loc_5970D
0x59707  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5970c  throw
0x5970d  ldarg.0
0x5970e  ldstr    aCheckedoutbyus// "CheckedOutByUser"
0x59713  ldarg.s  4
0x59715  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5971a  ldc.i4.1
0x5971b  stloc.0
0x5971c  ldarg.0
0x5971d  ldarg.1
0x5971e  ldloc.1
0x5971f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CheckedOutByUser()
0x59724  ldarg.3
0x59725  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5972a  ldarg.s  4
0x5972c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x59731  br       loc_5A192
0x59736  ldarg.3
0x59737  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5973c  stloc.s  0xA
0x5973e  ldloca.s 0xA
0x59740  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x59745  brfalse.s loc_5975E
0x59747  ldarg.3
0x59748  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5974d  stloc.s  0xB
0x5974f  ldloca.s 0xB
0x59751  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x59756  brtrue.s loc_5975E
0x59758  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5975d  throw
0x5975e  ldarg.0
0x5975f  ldstr    aCheckincomment_0// "CheckInComment"
0x59764  ldarg.s  4
0x59766  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5976b  ldc.i4.1
0x5976c  stloc.0
0x5976d  ldarg.1
0x5976e  ldloc.1
0x5976f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CheckInComment()
0x59774  ldarg.s  4
0x59776  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5977b  br       loc_5A192
0x59780  ldarg.3
0x59781  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x59786  stloc.s  0xC
0x59788  ldloca.s 0xC
0x5978a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5978f  brfalse.s loc_597A8
0x59791  ldarg.3
  ... truncated ...
```
