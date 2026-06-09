# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::Execute

- ea: `0xde00`
- end: `0xe0e5`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::Execute`
- size: `741`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0xde00`
- `0xe260`
- `0xe2b0`
- `0x65280`
- `0x65dd0`

## string_xrefs

- `0xdf7a`: `LastContentTypeHubUri`
- `0xe053`: `LastContentTypeHubUri`

## pseudocode

```c

```

## disassembly

```asm
0xde00  ldstr    aHubtimerjobdef// "HubTimerJobDefinition.Execute"
0xde05  ldc.i4   0x7562DC
0xde0a  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xde0f  ldc.i4   0x7562DD
0xde14  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xde19  ldc.i4   0x7562DE
0xde1e  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xde23  ldc.i4.0
0xde24  ldnull
0xde25  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0xde2a  stloc.0
0xde2b  ldarg.1
0xde2c  brtrue.s loc_DE39
0xde2e  ldstr    aJobstate// "jobState"
0xde33  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xde38  throw
0xde39  ldc.i4   0x38797135
0xde3e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xde43  ldc.i4.s 0x32
0xde45  ldstr    aMetadataHubTim// "Metadata Hub timer job starts."
0xde4a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xde4f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::.ctor()
0xde54  stloc.1
0xde55  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy> Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetProxies()
0xde5a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::GetEnumerator()
0xde5f  stloc.s  0xD
0xde61  br       loc_DF5D
0xde66  ldloca.s 0xD
0xde68  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::get_Current()
0xde6d  stloc.2
0xde6e  ldloc.2
0xde6f  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPObjectStatus [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Status()
0xde74  brfalse.s loc_DEBE
0xde76  ldloc.0
0xde77  ldc.i4   0x7562DF
0xde7c  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xde81  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xde86  ldstr    aSkippedProxy0B// "Skipped proxy {0} because it is not onl"...
0xde8b  ldc.i4.1
0xde8c  newarr   [mscorlib]System.Object
0xde91  stloc.s  0xE
0xde93  ldloc.s  0xE
0xde95  ldc.i4.0
0xde96  ldloc.2
0xde97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0xde9c  stloc.s  0xF
0xde9e  ldloca.s 0xF
0xdea0  constrained. [mscorlib]System.Guid
0xdea6  callvirt instance string [mscorlib]System.Object::ToString()
0xdeab  stelem.ref
0xdeac  ldloc.s  0xE
0xdeae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdeb3  ldnull
0xdeb4  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0xdeb9  br       loc_DF5D
0xdebe  ldloc.2
0xdebf  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetIsServiceApplicationPartitioned()
0xdec4  brtrue.s loc_DED0
0xdec6  ldloc.2
0xdec7  ldnull
0xdec8  ldloc.1
0xdec9  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::PopulateMap(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription siteSubscription, class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>> map)
0xdece  br.s     loc_DF18
0xded0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0xded5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_SiteSubscriptions()
0xdeda  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0xdedf  stloc.s  0x10
0xdee1  br.s     loc_DEF8
0xdee3  ldloc.s  0x10
0xdee5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xdeea  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription
0xdeef  stloc.3
0xdef0  ldloc.2
0xdef1  ldloc.3
0xdef2  ldloc.1
0xdef3  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::PopulateMap(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription siteSubscription, class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>> map)
0xdef8  ldloc.s  0x10
0xdefa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xdeff  brtrue.s loc_DEE3
0xdf01  leave.s  loc_DF18
0xdf03  ldloc.s  0x10
0xdf05  isinst   [mscorlib]System.IDisposable
0xdf0a  stloc.s  0x11
0xdf0c  ldloc.s  0x11
0xdf0e  brfalse.s loc_DF17
0xdf10  ldloc.s  0x11
0xdf12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdf17  endfinally
0xdf18  leave.s  loc_DF5D
0xdf1a  stloc.s  4
0xdf1c  ldloc.0
0xdf1d  ldc.i4   0x7562E0
0xdf22  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xdf27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdf2c  ldstr    aProxy0ThrowsAn// "Proxy {0} throws an exception: {1}"
0xdf31  ldc.i4.2
0xdf32  newarr   [mscorlib]System.Object
0xdf37  stloc.s  0x12
0xdf39  ldloc.s  0x12
0xdf3b  ldc.i4.0
0xdf3c  ldloc.2
0xdf3d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xdf42  stelem.ref
0xdf43  ldloc.s  0x12
0xdf45  ldc.i4.1
0xdf46  ldloc.s  4
0xdf48  callvirt instance string [mscorlib]System.Object::ToString()
0xdf4d  stelem.ref
0xdf4e  ldloc.s  0x12
0xdf50  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdf55  ldnull
0xdf56  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0xdf5b  leave.s  loc_DF5D
0xdf5d  ldloca.s 0xD
0xdf5f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::MoveNext()
0xdf64  brtrue   loc_DE66
0xdf69  leave.s  loc_DF79
0xdf6b  ldloca.s 0xD
0xdf6d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>
0xdf73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdf78  endfinally
0xdf79  ldarg.1
0xdf7a  ldstr    aLastcontenttyp// "LastContentTypeHubUri"
0xdf7f  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobState::get_Item(string)
0xdf84  isinst   [mscorlib]System.String
0xdf89  stloc.s  5
0xdf8b  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, class [System]System.Uri>::.ctor()
0xdf90  stloc.s  6
0xdf92  ldloc.1
0xdf93  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::get_Keys()
0xdf98  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::GetEnumerator()
0xdf9d  stloc.s  0x13
0xdf9f  br.s     loc_DFBA
0xdfa1  ldloca.s 0x13
0xdfa3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::get_Current()
0xdfa8  stloc.s  7
0xdfaa  ldloc.s  6
0xdfac  ldloc.s  7
0xdfae  callvirt instance string [mscorlib]System.Object::ToString()
0xdfb3  ldloc.s  7
0xdfb5  callvirt instance void class [System]System.Collections.Generic.SortedList`2<string, class [System]System.Uri>::Add(var<u1>, !!T0)
0xdfba  ldloca.s 0x13
0xdfbc  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::MoveNext()
0xdfc1  brtrue.s loc_DFA1
0xdfc3  leave.s  loc_DFD3
0xdfc5  ldloca.s 0x13
0xdfc7  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>
0xdfcd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdfd2  endfinally
0xdfd3  ldloc.1
0xdfd4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::get_Keys()
0xdfd9  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::get_Count()
0xdfde  ldc.i4.s 0x14
0xdfe0  div
0xdfe1  stloc.s  8
0xdfe3  ldloc.s  8
0xdfe5  brtrue.s loc_DFEA
0xdfe7  ldc.i4.1
0xdfe8  stloc.s  8
0xdfea  ldloc.s  5
0xdfec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdff1  ldc.i4.0
0xdff2  ceq
0xdff4  stloc.s  9
0xdff6  ldc.i4.0
0xdff7  stloc.s  0xA
0xdff9  ldloc.s  6
0xdffb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [System]System.Collections.Generic.SortedList`2<string, class [System]System.Uri>::GetEnumerator()
0xe000  stloc.s  0x14
0xe002  br       loc_E092
0xe007  ldloc.s  0x14
0xe009  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Uri>>::get_Current()
0xe00e  stloc.s  0xB
0xe010  ldarg.1
0xe011  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobState::get_ShouldStop()
0xe016  brfalse.s loc_E01D
0xe018  leave    loc_E0E4
0xe01d  ldloc.s  9
0xe01f  brfalse.s loc_E039
0xe021  ldloc.s  6
0xe023  callvirt instance class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class [System]System.Uri>::get_Comparer()
0xe028  ldloca.s 0xB
0xe02a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Uri>::get_Key()
0xe02f  ldloc.s  5
0xe031  callvirt instance int32 class [mscorlib]System.Collections.Generic.IComparer`1<string>::Compare(var<u1>, !!T0)
0xe036  ldc.i4.0
0xe037  ble.s    loc_E064
0xe039  ldloca.s 0xB
0xe03b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Uri>::get_Value()
0xe040  ldloc.1
0xe041  ldloca.s 0xB
0xe043  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Uri>::get_Value()
0xe048  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::get_Item(void)
0xe04d  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::ProcessHubSite(class [System]System.Uri hubSiteUrl, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy> proxyList)
0xe052  ldarg.1
0xe053  ldstr    aLastcontenttyp// "LastContentTypeHubUri"
0xe058  ldloca.s 0xB
0xe05a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Uri>::get_Key()
0xe05f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobState::set_Item(string, object)
0xe064  ldloc.s  0xA
0xe066  ldc.i4.1
0xe067  add.ovf
0xe068  stloc.s  0xA
0xe06a  ldloc.s  0xA
0xe06c  ldloc.s  8
0xe06e  rem
0xe06f  brtrue.s loc_E092
0xe071  ldloc.s  0xA
0xe073  conv.r4
0xe074  ldloc.1
0xe075  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::get_Keys()
0xe07a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [System]System.Uri, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>>::get_Count()
0xe07f  conv.r4
0xe080  div
0xe081  ldc.r4   100.0
0xe086  mul
0xe087  stloc.s  0xC
0xe089  ldarg.0
0xe08a  ldloc.s  0xC
0xe08c  conv.ovf.i2.un
0xe08d  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::UpdateProgress(int32)
0xe092  ldloc.s  0x14
0xe094  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe099  brtrue   loc_E007
0xe09e  leave.s  loc_E0AC
0xe0a0  ldloc.s  0x14
0xe0a2  brfalse.s loc_E0AB
0xe0a4  ldloc.s  0x14
0xe0a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe0ab  endfinally
0xe0ac  ldloc.s  0xA
0xe0ae  ldloc.s  8
0xe0b0  rem
0xe0b1  brfalse.s loc_E0BB
0xe0b3  ldarg.0
0xe0b4  ldc.i4.s 0x64
0xe0b6  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::UpdateProgress(int32)
0xe0bb  ldc.i4   0x38797136
0xe0c0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe0c5  ldc.i4.s 0x32
0xe0c7  ldstr    aMetadataHubTim_0// "Metadata Hub timer job ends."
0xe0cc  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xe0d1  ldloc.0
0xe0d2  ldnull
0xe0d3  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::Success(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0xe0d8  leave.s  loc_E0E4
0xe0da  ldloc.0
0xe0db  brfalse.s loc_E0E3
0xe0dd  ldloc.0
0xe0de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe0e3  endfinally
0xe0e4  ret
```
