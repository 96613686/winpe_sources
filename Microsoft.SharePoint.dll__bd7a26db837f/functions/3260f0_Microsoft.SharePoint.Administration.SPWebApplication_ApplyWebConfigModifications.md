# Microsoft.SharePoint.Administration.SPWebApplication::ApplyWebConfigModifications

- ea: `0x3260f0`
- end: `0x326552`
- name: `Microsoft.SharePoint.Administration.SPWebApplication::ApplyWebConfigModifications`
- size: `1122`
- prototype: ``
- caller_count: `5`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2302e0`
- `0x230410`
- `0x323800`
- `0x326560`
- `0x32e3e0`

## callees

- `0x1b7de0`
- `0x1c8480`
- `0x1c8540`
- `0x1c8680`
- `0x1c8850`
- `0x1c89b0`
- `0x1c8a20`
- `0x22f9d0`
- `0x22fa00`
- `0x22fa30`
- `0x22fa80`
- `0x22fc40`
- `0x22fc60`
- `0x22fd70`
- `0x237b40`
- `0x249550`
- `0x24a520`
- `0x2a01d0`
- `0x2eb850`
- `0x31d490`
- `0x31d770`
- `0x323760`
- `0x3260f0`
- `0x32d2f0`
- `0x577060`
- `0x93dae0`
- `0x957470`
- `0x957530`

## string_xrefs

- `0x32623c`: `web.config`
- `0x326395`: `FailedToSaveWebConfig`
- `0x326103`: `WebConfigModification: Skipping web config modifications for web app {0} in server {1} since IIBlast is enabled.`
- `0x326155`: `WebConfigModification: Applying web config modifications to web app {0} in server {1}`
- `0x32625d`: `WebConfigModification: Missing web.config file {0} for applying modifications to web app {1} `
- `0x326292`: `WebConfigModification: Applying web config modifications to file {0} `
- `0x3262df`: `WebConfigModification: Applying WebConfigModifications FAILED for web.config file {0} for web app {1}. Exception message - {2}`
- `0x32630f`: `WebConfigModificationError`
- `0x326365`: `WebConfigModification: Save of web.config file {0} for applying modifications to web app {1} failed. Error message - {2}`
- `0x3263dd`: `WebConfigModification: Saved web config file {0} `
- `0x326491`: `WebConfigModification: Different web config modifications applied to web app {0} in farm. Server {1}`
- `0x3264d1`: `WebConfigModification: FileChanges that store the web config modifications applied to web app {0} in server {1} cannot be saved. There might be a problem removing them next time.`
- `0x326513`: `WebConfigModification: Changes not applied to web application {0} with Url {1}`

## pseudocode

```c

```

## disassembly

```asm
0x3260f0  ldsfld   bool Microsoft.SharePoint.Administration.SPIisProvisioningAssistant::StaticDeploymentEnabled
0x3260f5  brfalse.s loc_326136
0x3260f7  ldc.i4   0x3867726E
0x3260fc  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x326101  ldc.i4.s 0x14
0x326103  ldstr    aWebconfigmodif_9// "WebConfigModification: Skipping web con"...
0x326108  ldc.i4.2
0x326109  newarr   [mscorlib]System.Object
0x32610e  stloc.s  0xD
0x326110  ldloc.s  0xD
0x326112  ldc.i4.0
0x326113  ldarg.0
0x326114  ldc.i4.0
0x326115  call     instance class [System]System.Uri Microsoft.SharePoint.Administration.SPWebApplication::GetResponseUri(valuetype Microsoft.SharePoint.Administration.SPUrlZone zone)
0x32611a  callvirt instance string [mscorlib]System.Object::ToString()
0x32611f  stelem.ref
0x326120  ldloc.s  0xD
0x326122  ldc.i4.1
0x326123  call     class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPServer::get_Local()
0x326128  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x32612d  stelem.ref
0x32612e  ldloc.s  0xD
0x326130  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x326135  ret
0x326136  call     class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPServer::get_Local()
0x32613b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x326140  stloc.0
0x326141  ldsfld   string [mscorlib]System.String::Empty
0x326146  stloc.1
0x326147  ldc.i4.0
0x326148  stloc.2
0x326149  ldc.i4   0x4451CE
0x32614e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x326153  ldc.i4.s 0x32
0x326155  ldstr    aWebconfigmodif_10// "WebConfigModification: Applying web con"...
0x32615a  ldc.i4.2
0x32615b  newarr   [mscorlib]System.Object
0x326160  stloc.s  0xE
0x326162  ldloc.s  0xE
0x326164  ldc.i4.0
0x326165  ldarg.0
0x326166  ldc.i4.0
0x326167  call     instance class [System]System.Uri Microsoft.SharePoint.Administration.SPWebApplication::GetResponseUri(valuetype Microsoft.SharePoint.Administration.SPUrlZone zone)
0x32616c  callvirt instance string [mscorlib]System.Object::ToString()
0x326171  stelem.ref
0x326172  ldloc.s  0xE
0x326174  ldc.i4.1
0x326175  call     class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPServer::get_Local()
0x32617a  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x32617f  stelem.ref
0x326180  ldloc.s  0xE
0x326182  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x326187  ldarg.0
0x326188  call     instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x32618d  ldloc.0
0x32618e  call     string Microsoft.SharePoint.Administration.SPWebConfigFileChanges::GenerateName(valuetype [mscorlib]System.Guid serverId)
0x326193  ldarg.0
0x326194  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x326199  ldtoken  Microsoft.SharePoint.Administration.SPWebConfigFileChanges
0x32619e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3261a3  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPFarm::GetObject(string name, valuetype [mscorlib]System.Guid parentId, class [mscorlib]System.Type type)
0x3261a8  castclass Microsoft.SharePoint.Administration.SPWebConfigFileChanges
0x3261ad  stloc.3
0x3261ae  ldnull
0x3261af  ldloc.3
0x3261b0  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x3261b5  brfalse.s loc_3261BF
0x3261b7  ldloc.0
0x3261b8  ldarg.0
0x3261b9  newobj   instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::.ctor(valuetype [mscorlib]System.Guid serverId, class Microsoft.SharePoint.Administration.SPWebApplication web)
0x3261be  stloc.3
0x3261bf  ldloc.0
0x3261c0  ldarg.0
0x3261c1  newobj   instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::.ctor(valuetype [mscorlib]System.Guid serverId, class Microsoft.SharePoint.Administration.SPWebApplication web)
0x3261c6  stloc.s  4
0x3261c8  ldloc.s  4
0x3261ca  ldarg.0
0x3261cb  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> Microsoft.SharePoint.Administration.SPWebApplication::get_WebConfigModifications()
0x3261d0  callvirt instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::RebuildListModifications(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> changes)
0x3261d5  ldarg.0
0x3261d6  call     instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPPersistedObject::get_Parent()
0x3261db  castclass Microsoft.SharePoint.Administration.SPWebService
0x3261e0  stloc.s  5
0x3261e2  ldloc.s  4
0x3261e4  ldloc.s  5
0x3261e6  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> Microsoft.SharePoint.Administration.SPWebService::get_WebConfigModifications()
0x3261eb  callvirt instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::AddListModifications(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> changes)
0x3261f0  ldarg.0
0x3261f1  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings> Microsoft.SharePoint.Administration.SPWebApplication::get_IisSettings()
0x3261f6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::get_Values()
0x3261fb  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::GetEnumerator()
0x326200  stloc.s  0xF
0x326202  br       loc_3263F7
0x326207  ldloca.s 0xF
0x326209  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::get_Current()
0x32620e  stloc.s  6
0x326210  ldloc.s  6
0x326212  callvirt instance class [mscorlib]System.IO.DirectoryInfo Microsoft.SharePoint.Administration.SPIisSettings::get_Path()
0x326217  callvirt instance string [mscorlib]System.Object::ToString()
0x32621c  stloc.s  7
0x32621e  ldloc.s  7
0x326220  ldstr    asc_CA2654// "\\"
0x326225  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x32622a  brtrue.s loc_32623A
0x32622c  ldloc.s  7
0x32622e  ldstr    asc_CA2654// "\\"
0x326233  call     string [mscorlib]System.String::Concat(string, string)
0x326238  stloc.s  7
0x32623a  ldloc.s  7
0x32623c  ldstr    aWebConfig_0// "web.config"
0x326241  call     string [mscorlib]System.String::Concat(string, string)
0x326246  stloc.s  7
0x326248  ldloc.s  7
0x32624a  call     bool [mscorlib]System.IO.File::Exists(string)
0x32624f  brtrue.s loc_326286
0x326251  ldc.i4   0x39377231
0x326256  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32625b  ldc.i4.s 0x32
0x32625d  ldstr    aWebconfigmodif_11// "WebConfigModification: Missing web.conf"...
0x326262  ldc.i4.2
0x326263  newarr   [mscorlib]System.Object
0x326268  stloc.s  0x10
0x32626a  ldloc.s  0x10
0x32626c  ldc.i4.0
0x32626d  ldloc.s  7
0x32626f  stelem.ref
0x326270  ldloc.s  0x10
0x326272  ldc.i4.1
0x326273  ldarg.0
0x326274  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x326279  stelem.ref
0x32627a  ldloc.s  0x10
0x32627c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x326281  br       loc_3263F7
0x326286  ldc.i4   0x38386777
0x32628b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x326290  ldc.i4.s 0x32
0x326292  ldstr    aWebconfigmodif_12// "WebConfigModification: Applying web con"...
0x326297  ldc.i4.1
0x326298  newarr   [mscorlib]System.Object
0x32629d  stloc.s  0x11
0x32629f  ldloc.s  0x11
0x3262a1  ldc.i4.0
0x3262a2  ldloc.s  7
0x3262a4  stelem.ref
0x3262a5  ldloc.s  0x11
0x3262a7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x3262ac  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x3262b1  stloc.s  8
0x3262b3  ldloc.s  8
0x3262b5  ldloc.s  7
0x3262b7  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(string)
0x3262bc  ldloc.3
0x3262bd  ldloc.s  8
0x3262bf  callvirt instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::RemoveModificationsWebConfigXmlDocument(class [System.Xml]System.Xml.XmlDocument xdWebConfig)
0x3262c4  ldloc.s  4
0x3262c6  ldloc.s  8
0x3262c8  ldloc.s  7
0x3262ca  callvirt instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::ApplyModificationsWebConfigXmlDocument(class [System.Xml]System.Xml.XmlDocument xdWebConfig, string filepath)
0x3262cf  leave.s  loc_32634C
0x3262d1  stloc.s  9
0x3262d3  ldc.i4   0x66366B67
0x3262d8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3262dd  ldc.i4.s 0x14
0x3262df  ldstr    aWebconfigmodif_13// "WebConfigModification: Applying WebConf"...
0x3262e4  ldc.i4.3
0x3262e5  newarr   [mscorlib]System.Object
0x3262ea  stloc.s  0x12
0x3262ec  ldloc.s  0x12
0x3262ee  ldc.i4.0
0x3262ef  ldloc.s  7
0x3262f1  stelem.ref
0x3262f2  ldloc.s  0x12
0x3262f4  ldc.i4.1
0x3262f5  ldarg.0
0x3262f6  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x3262fb  stelem.ref
0x3262fc  ldloc.s  0x12
0x3262fe  ldc.i4.2
0x3262ff  ldloc.s  9
0x326301  callvirt instance string [mscorlib]System.Exception::get_Message()
0x326306  stelem.ref
0x326307  ldloc.s  0x12
0x326309  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x32630e  ldloc.1
0x32630f  ldstr    aWebconfigmodif_14// "WebConfigModificationError"
0x326314  ldc.i4.1
0x326315  newarr   [mscorlib]System.Object
0x32631a  stloc.s  0x13
0x32631c  ldloc.s  0x13
0x32631e  ldc.i4.0
0x32631f  ldloc.s  7
0x326321  stelem.ref
0x326322  ldloc.s  0x13
0x326324  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x326329  ldstr    asc_C78520// "\r\n"
0x32632e  call     string [mscorlib]System.String::Concat(string, string, string)
0x326333  stloc.1
0x326334  ldloc.1
0x326335  ldloc.s  9
0x326337  callvirt instance string [mscorlib]System.Exception::get_Message()
0x32633c  ldstr    asc_C78520// "\r\n"
0x326341  call     string [mscorlib]System.String::Concat(string, string, string)
0x326346  stloc.1
0x326347  leave    loc_3263F7
0x32634c  ldloc.s  8
0x32634e  ldloc.s  7
0x326350  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(string)
0x326355  leave.s  loc_3263CF
0x326357  stloc.s  0xA
0x326359  ldc.i4   0x66366B68
0x32635e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x326363  ldc.i4.s 0x14
0x326365  ldstr    aWebconfigmodif_15// "WebConfigModification: Save of web.conf"...
0x32636a  ldc.i4.3
0x32636b  newarr   [mscorlib]System.Object
0x326370  stloc.s  0x14
0x326372  ldloc.s  0x14
0x326374  ldc.i4.0
0x326375  ldloc.s  7
0x326377  stelem.ref
0x326378  ldloc.s  0x14
0x32637a  ldc.i4.1
0x32637b  ldarg.0
0x32637c  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x326381  stelem.ref
0x326382  ldloc.s  0x14
0x326384  ldc.i4.2
0x326385  ldloc.s  0xA
0x326387  callvirt instance string [mscorlib]System.Exception::get_Message()
0x32638c  stelem.ref
0x32638d  ldloc.s  0x14
0x32638f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x326394  ldloc.1
0x326395  ldstr    aFailedtosavewe// "FailedToSaveWebConfig"
0x32639a  ldc.i4.1
0x32639b  newarr   [mscorlib]System.Object
0x3263a0  stloc.s  0x15
0x3263a2  ldloc.s  0x15
0x3263a4  ldc.i4.0
0x3263a5  ldloc.s  7
0x3263a7  stelem.ref
0x3263a8  ldloc.s  0x15
0x3263aa  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x3263af  ldstr    asc_C78520// "\r\n"
0x3263b4  call     string [mscorlib]System.String::Concat(string, string, string)
0x3263b9  stloc.1
0x3263ba  ldloc.1
0x3263bb  ldloc.s  0xA
0x3263bd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3263c2  ldstr    asc_C78520// "\r\n"
0x3263c7  call     string [mscorlib]System.String::Concat(string, string, string)
0x3263cc  stloc.1
0x3263cd  leave.s  loc_3263F7
0x3263cf  ldc.i4.1
0x3263d0  stloc.2
0x3263d1  ldc.i4   0x38386778
0x3263d6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3263db  ldc.i4.s 0x32
0x3263dd  ldstr    aWebconfigmodif_16// "WebConfigModification: Saved web config"...
0x3263e2  ldc.i4.1
0x3263e3  newarr   [mscorlib]System.Object
0x3263e8  stloc.s  0x16
0x3263ea  ldloc.s  0x16
0x3263ec  ldc.i4.0
0x3263ed  ldloc.s  7
0x3263ef  stelem.ref
0x3263f0  ldloc.s  0x16
0x3263f2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x3263f7  ldloca.s 0xF
0x3263f9  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::MoveNext()
0x3263fe  brtrue   loc_326207
0x326403  leave.s  loc_326413
0x326405  ldloca.s 0xF
0x326407  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>
0x32640d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x326412  endfinally
0x326413  ldloc.2
0x326414  brfalse  loc_326507
0x326419  ldloc.3
0x32641a  ldarg.0
0x32641b  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> Microsoft.SharePoint.Administration.SPWebApplication::get_WebConfigModifications()
0x326420  callvirt instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::RebuildListModifications(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> changes)
0x326425  ldloc.3
0x326426  ldloc.s  5
0x326428  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> Microsoft.SharePoint.Administration.SPWebService::get_WebConfigModifications()
0x32642d  callvirt instance void Microsoft.SharePoint.Administration.SPWebConfigFileChanges::AddListModifications(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Administration.SPWebConfigModification> changes)
0x326432  ldloc.3
0x326433  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x326438  leave    loc_326541
0x32643d  stloc.s  0xB
0x32643f  ldloc.s  0xB
0x326441  isinst   Microsoft.SharePoint.Administration.SPUpdatedConcurrencyException
0x326446  brtrue.s loc_326451
0x326448  ldloc.s  0xB
0x32644a  isinst   Microsoft.SharePoint.Administration.SPDuplicateObjectException
0x32644f  brfalse.s loc_3264C5
0x326451  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x326456  ldloc.0
0x326457  call     string Microsoft.SharePoint.Administration.SPWebConfigFileChanges::GenerateName(valuetype [mscorlib]System.Guid serverId)
  ... truncated ...
```
