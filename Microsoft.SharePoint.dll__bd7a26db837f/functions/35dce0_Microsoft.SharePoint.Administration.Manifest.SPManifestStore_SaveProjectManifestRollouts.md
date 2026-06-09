# Microsoft.SharePoint.Administration.Manifest.SPManifestStore::SaveProjectManifestRollouts

- ea: `0x35dce0`
- end: `0x35e1fe`
- name: `Microsoft.SharePoint.Administration.Manifest.SPManifestStore::SaveProjectManifestRollouts`
- size: `1310`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2cbad0`
- `0x35cf20`
- `0x35d000`
- `0x35d040`
- `0x35d060`
- `0x35d600`
- `0x35d9e0`
- `0x35da00`
- `0x35da20`
- `0x35da40`
- `0x35da60`
- `0x35da80`
- `0x35daa0`
- `0x35dab0`
- `0x35db30`
- `0x35db50`
- `0x35dce0`
- `0x35e8b0`
- `0x35ef50`
- `0x93dab0`
- `0x93dae0`
- `0x957510`

## string_xrefs

- `0x35dcec`: `SaveProjectManifestRollouts: starting...`
- `0x35dd1f`: `SaveProjectManifestRollouts: GridFarmId or GridFarmLabel is not defined in SPFarmInitializationSettings.`
- `0x35dd2d`: `No manifests needed to be saved`
- `0x35dd6a`: `SaveProjectManifestRollouts: Processing [Project={0}, AllowDogfood={1}].`
- `0x35ddbd`: `OldManifests`
- `0x35ddcd`: `NewManifests`
- `0x35ddf5`: `SaveProjectManifestRollouts: Project [{0}] has no new manifest to be saved.`
- `0x35de1b`: `NULL oldManifestInfo`
- `0x35de33`: `SaveProjectManifestRollouts: Comparing manifests Old [Id={0}, CreateDate={1}] with New [Id={2}, CreateDate={3}].`
- `0x35de9a`: `Old ManifestId={0}, New ManifestId={1}`
- `0x35df01`: `Old CreateDate={0}, New CreateDate={1}`
- `0x35df42`: `SaveProjectManifestRollouts: Project [{0}] hasManifestChangedReason [{1}].`
- `0x35df8e`: `SaveProjectManifestRollouts: ProjectManifestRolloutInput [ManifestId={0}, ManifestName={1}, BuildNumber={2}, Project={3}, FarmId={4}, FarmLabel={5}, RolloutDate={6}].`
- `0x35e04a`: `SaveProjectManifestRollouts: Unexpected exception processing Project [{0}]: {1} - {2}.`
- `0x35e0a2`: `SaveProjectManifestRollouts: found [{0}] new rollouts to save to ManifestServer.`
- `0x35e0ee`: `SaveProjectManifestRollouts: Calling UpdateManifestsToServer [Attempt={0}].`
- `0x35e12d`: `SaveProjectManifestRollouts: Call to UpdateManifestsToServer succeeded [Attempt={0}].`
- `0x35e194`: `SaveProjectManifestRollouts: Call to UpdateManifestsToServer returned [{0}].`
- `0x35e1e3`: `SaveProjectManifestRollouts: done [{0}].`

## pseudocode

```c

```

## disassembly

```asm
0x35dce0  ldc.i4   0x1352252
0x35dce5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Timer()
0x35dcea  ldc.i4.s 0xF
0x35dcec  ldstr    aSaveprojectman_2// "SaveProjectManifestRollouts: starting.."...
0x35dcf1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x35dcf6  ldarg.3
0x35dcf7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.Manifest.ProjectManifestRolloutInput>::.ctor()
0x35dcfc  stind.ref
0x35dcfd  ldarg.0
0x35dcfe  call     instance int32 Microsoft.SharePoint.Administration.Manifest.SPManifestStore::get_GridFarmId()
0x35dd03  ldc.i4.0
0x35dd04  ble.s    loc_35DD13
0x35dd06  ldarg.0
0x35dd07  call     instance string Microsoft.SharePoint.Administration.Manifest.SPManifestStore::get_GridFarmLabel()
0x35dd0c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35dd11  brfalse.s loc_35DD2B
0x35dd13  ldc.i4   0x139B150
0x35dd18  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Timer()
0x35dd1d  ldc.i4.s 0x14
0x35dd1f  ldstr    aSaveprojectman_3// "SaveProjectManifestRollouts: GridFarmId"...
0x35dd24  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x35dd29  ldc.i4.1
0x35dd2a  ret
0x35dd2b  ldc.i4.0
0x35dd2c  stloc.0
0x35dd2d  ldstr    aNoManifestsNee// "No manifests needed to be saved"
0x35dd32  stloc.1
0x35dd33  call     int32 Microsoft.SharePoint.Administration.Manifest.SPOManifestSynchronizer::GetSiteHashValue()
0x35dd38  stloc.2
0x35dd39  call     bool Microsoft.SharePoint.Administration.SPManifests::get_AllowDogfood()
0x35dd3e  stloc.3
0x35dd3f  ldarg.2
0x35dd40  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo>>::GetEnumerator()
0x35dd45  stloc.s  0x14
0x35dd47  br       loc_35E07C
0x35dd4c  ldloc.s  0x14
0x35dd4e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo>>::get_Current()
0x35dd53  stloc.s  4
0x35dd55  ldloca.s 4
0x35dd57  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo>::get_Key()
0x35dd5c  stloc.s  5
0x35dd5e  ldc.i4   0x16105D7
0x35dd63  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Timer()
0x35dd68  ldc.i4.s 0x32
0x35dd6a  ldstr    aSaveprojectman_4// "SaveProjectManifestRollouts: Processing"...
0x35dd6f  ldc.i4.2
0x35dd70  newarr   [mscorlib]System.Object
0x35dd75  stloc.s  0x15
0x35dd77  ldloc.s  0x15
0x35dd79  ldc.i4.0
0x35dd7a  ldloc.s  5
0x35dd7c  stelem.ref
0x35dd7d  ldloc.s  0x15
0x35dd7f  ldc.i4.1
0x35dd80  ldloc.3
0x35dd81  box      [mscorlib]System.Boolean
0x35dd86  stelem.ref
0x35dd87  ldloc.s  0x15
0x35dd89  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x35dd8e  ldnull
0x35dd8f  stloc.s  6
0x35dd91  ldarg.1
0x35dd92  brfalse.s loc_35DDA8
0x35dd94  ldarg.1
0x35dd95  ldloc.s  5
0x35dd97  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo>::ContainsKey(var<u1>)
0x35dd9c  brfalse.s loc_35DDA8
0x35dd9e  ldarg.1
0x35dd9f  ldloc.s  5
0x35dda1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo>::get_Item(void)
0x35dda6  stloc.s  6
0x35dda8  ldloca.s 4
0x35ddaa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo>::get_Value()
0x35ddaf  stloc.s  7
0x35ddb1  ldnull
0x35ddb2  stloc.s  8
0x35ddb4  ldnull
0x35ddb5  stloc.s  9
0x35ddb7  ldloc.s  6
0x35ddb9  brfalse.s loc_35DDCB
0x35ddbb  ldloc.s  6
0x35ddbd  ldstr    aOldmanifests// "OldManifests"
0x35ddc2  ldloc.3
0x35ddc3  ldloc.2
0x35ddc4  callvirt instance class Microsoft.SharePoint.Administration.Manifest.ManifestInfo Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo::DetermineManifest(string manifestType, bool allowDogfood, int32 hashValue)
0x35ddc9  stloc.s  8
0x35ddcb  ldloc.s  7
0x35ddcd  ldstr    aNewmanifests// "NewManifests"
0x35ddd2  ldloc.3
0x35ddd3  ldloc.2
0x35ddd4  callvirt instance class Microsoft.SharePoint.Administration.Manifest.ManifestInfo Microsoft.SharePoint.Administration.Manifest.ProjectManifestInfo::DetermineManifest(string manifestType, bool allowDogfood, int32 hashValue)
0x35ddd9  stloc.s  9
0x35dddb  ldc.i4.0
0x35dddc  stloc.s  0xA
0x35ddde  ldsfld   string [mscorlib]System.String::Empty
0x35dde3  stloc.s  0xB
0x35dde5  ldloc.s  9
0x35dde7  brtrue.s loc_35DE14
0x35dde9  ldc.i4   0x16105D8
0x35ddee  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Timer()
0x35ddf3  ldc.i4.s 0x32
0x35ddf5  ldstr    aSaveprojectman_5// "SaveProjectManifestRollouts: Project [{"...
0x35ddfa  ldc.i4.1
0x35ddfb  newarr   [mscorlib]System.Object
0x35de00  stloc.s  0x16
0x35de02  ldloc.s  0x16
0x35de04  ldc.i4.0
0x35de05  ldloc.s  5
0x35de07  stelem.ref
0x35de08  ldloc.s  0x16
0x35de0a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x35de0f  br       loc_35DF2D
0x35de14  ldloc.s  8
0x35de16  brtrue.s loc_35DE27
0x35de18  ldc.i4.1
0x35de19  stloc.s  0xA
0x35de1b  ldstr    aNullOldmanifes_0// "NULL oldManifestInfo"
0x35de20  stloc.s  0xB
0x35de22  br       loc_35DF2D
0x35de27  ldc.i4   0x215245F
0x35de2c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Timer()
0x35de31  ldc.i4.s 0x32
0x35de33  ldstr    aSaveprojectman_6// "SaveProjectManifestRollouts: Comparing "...
0x35de38  ldc.i4.4
0x35de39  newarr   [mscorlib]System.Object
0x35de3e  stloc.s  0x17
0x35de40  ldloc.s  0x17
0x35de42  ldc.i4.0
0x35de43  ldloc.s  8
0x35de45  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_ManifestId()
0x35de4a  box      [mscorlib]System.Guid
0x35de4f  stelem.ref
0x35de50  ldloc.s  0x17
0x35de52  ldc.i4.1
0x35de53  ldloc.s  8
0x35de55  callvirt instance string Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_CreateDateString()
0x35de5a  stelem.ref
0x35de5b  ldloc.s  0x17
0x35de5d  ldc.i4.2
0x35de5e  ldloc.s  9
0x35de60  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_ManifestId()
0x35de65  box      [mscorlib]System.Guid
0x35de6a  stelem.ref
0x35de6b  ldloc.s  0x17
0x35de6d  ldc.i4.3
0x35de6e  ldloc.s  9
0x35de70  callvirt instance string Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_CreateDateString()
0x35de75  stelem.ref
0x35de76  ldloc.s  0x17
0x35de78  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x35de7d  ldloc.s  8
0x35de7f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_ManifestId()
0x35de84  ldloc.s  9
0x35de86  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_ManifestId()
0x35de8b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x35de90  brfalse.s loc_35DED2
0x35de92  ldc.i4.1
0x35de93  stloc.s  0xA
0x35de95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35de9a  ldstr    aOldManifestid0// "Old ManifestId={0}, New ManifestId={1}"
0x35de9f  ldc.i4.2
0x35dea0  newarr   [mscorlib]System.Object
0x35dea5  stloc.s  0x18
0x35dea7  ldloc.s  0x18
0x35dea9  ldc.i4.0
0x35deaa  ldloc.s  8
0x35deac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_ManifestId()
0x35deb1  box      [mscorlib]System.Guid
0x35deb6  stelem.ref
0x35deb7  ldloc.s  0x18
0x35deb9  ldc.i4.1
0x35deba  ldloc.s  9
0x35debc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_ManifestId()
0x35dec1  box      [mscorlib]System.Guid
0x35dec6  stelem.ref
0x35dec7  ldloc.s  0x18
0x35dec9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35dece  stloc.s  0xB
0x35ded0  br.s     loc_35DF2D
0x35ded2  ldloc.s  9
0x35ded4  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_CreateDate()
0x35ded9  ldloc.s  8
0x35dedb  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_CreateDate()
0x35dee0  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x35dee5  stloc.s  0x19
0x35dee7  ldloca.s 0x19
0x35dee9  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x35deee  ldc.r8   1.0
0x35def7  ble.un.s loc_35DF2D
0x35def9  ldc.i4.1
0x35defa  stloc.s  0xA
0x35defc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35df01  ldstr    aOldCreatedate0// "Old CreateDate={0}, New CreateDate={1}"
0x35df06  ldc.i4.2
0x35df07  newarr   [mscorlib]System.Object
0x35df0c  stloc.s  0x1A
0x35df0e  ldloc.s  0x1A
0x35df10  ldc.i4.0
0x35df11  ldloc.s  8
0x35df13  callvirt instance string Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_CreateDateString()
0x35df18  stelem.ref
0x35df19  ldloc.s  0x1A
0x35df1b  ldc.i4.1
0x35df1c  ldloc.s  9
0x35df1e  callvirt instance string Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_CreateDateString()
0x35df23  stelem.ref
0x35df24  ldloc.s  0x1A
0x35df26  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35df2b  stloc.s  0xB
0x35df2d  ldloc.s  0xB
0x35df2f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35df34  brtrue.s loc_35DF62
0x35df36  ldc.i4   0x16105D9
0x35df3b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Timer()
0x35df40  ldc.i4.s 0x32
0x35df42  ldstr    aSaveprojectman_7// "SaveProjectManifestRollouts: Project [{"...
0x35df47  ldc.i4.2
0x35df48  newarr   [mscorlib]System.Object
0x35df4d  stloc.s  0x1B
0x35df4f  ldloc.s  0x1B
0x35df51  ldc.i4.0
0x35df52  ldloc.s  5
0x35df54  stelem.ref
0x35df55  ldloc.s  0x1B
0x35df57  ldc.i4.1
0x35df58  ldloc.s  0xB
0x35df5a  stelem.ref
0x35df5b  ldloc.s  0x1B
0x35df5d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x35df62  ldloc.s  0xA
0x35df64  brfalse  loc_35E03A
0x35df69  ldloc.s  9
0x35df6b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_ManifestId()
0x35df70  stloc.s  0xC
0x35df72  ldloc.s  9
0x35df74  callvirt instance string Microsoft.SharePoint.Administration.Manifest.ManifestInfo::get_RowKey()
0x35df79  stloc.s  0xD
0x35df7b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x35df80  stloc.s  0xE
0x35df82  ldc.i4   0x16105DA
0x35df87  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Timer()
0x35df8c  ldc.i4.s 0x32
0x35df8e  ldstr    aSaveprojectman_8// "SaveProjectManifestRollouts: ProjectMan"...
0x35df93  ldc.i4.7
0x35df94  newarr   [mscorlib]System.Object
0x35df99  stloc.s  0x1C
0x35df9b  ldloc.s  0x1C
0x35df9d  ldc.i4.0
0x35df9e  ldloc.s  0xC
0x35dfa0  box      [mscorlib]System.Guid
0x35dfa5  stelem.ref
0x35dfa6  ldloc.s  0x1C
0x35dfa8  ldc.i4.1
0x35dfa9  ldloc.s  0xD
0x35dfab  stelem.ref
0x35dfac  ldloc.s  0x1C
0x35dfae  ldc.i4.2
0x35dfaf  ldloc.s  0xD
0x35dfb1  stelem.ref
0x35dfb2  ldloc.s  0x1C
0x35dfb4  ldc.i4.3
0x35dfb5  ldloc.s  5
0x35dfb7  stelem.ref
0x35dfb8  ldloc.s  0x1C
0x35dfba  ldc.i4.4
0x35dfbb  ldarg.0
0x35dfbc  call     instance int32 Microsoft.SharePoint.Administration.Manifest.SPManifestStore::get_GridFarmId()
0x35dfc1  box      [mscorlib]System.Int32
0x35dfc6  stelem.ref
0x35dfc7  ldloc.s  0x1C
0x35dfc9  ldc.i4.5
0x35dfca  ldarg.0
0x35dfcb  call     instance string Microsoft.SharePoint.Administration.Manifest.SPManifestStore::get_GridFarmLabel()
0x35dfd0  stelem.ref
0x35dfd1  ldloc.s  0x1C
0x35dfd3  ldc.i4.6
0x35dfd4  ldloc.s  0xE
0x35dfd6  box      [mscorlib]System.DateTime
0x35dfdb  stelem.ref
0x35dfdc  ldloc.s  0x1C
0x35dfde  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x35dfe3  ldarg.3
0x35dfe4  ldind.ref
0x35dfe5  newobj   instance void Microsoft.SharePoint.Administration.Manifest.ProjectManifestRolloutInput::.ctor()
0x35dfea  stloc.s  0xF
0x35dfec  ldloc.s  0xF
0x35dfee  ldloc.s  0xC
0x35dff0  callvirt instance void Microsoft.SharePoint.Administration.Manifest.ProjectManifestRolloutInput::set_ManifestId(valuetype [mscorlib]System.Guid value)
0x35dff5  ldloc.s  0xF
0x35dff7  ldloc.s  0xD
0x35dff9  callvirt instance void Microsoft.SharePoint.Administration.Manifest.ProjectManifestRolloutInput::set_ManifestName(string value)
0x35dffe  ldloc.s  0xF
0x35e000  ldloc.s  0xD
0x35e002  callvirt instance void Microsoft.SharePoint.Administration.Manifest.ProjectManifestRolloutInput::set_BuildNumber(string value)
0x35e007  ldloc.s  0xF
0x35e009  ldloc.s  5
0x35e00b  callvirt instance void Microsoft.SharePoint.Administration.Manifest.ProjectManifestRolloutInput::set_Project(string value)
0x35e010  ldloc.s  0xF
0x35e012  ldarg.0
0x35e013  call     instance int32 Microsoft.SharePoint.Administration.Manifest.SPManifestStore::get_GridFarmId()
  ... truncated ...
```
