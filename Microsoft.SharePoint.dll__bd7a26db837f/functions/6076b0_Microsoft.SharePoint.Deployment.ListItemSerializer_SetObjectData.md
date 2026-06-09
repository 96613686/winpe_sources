# Microsoft.SharePoint.Deployment.ListItemSerializer::SetObjectData

- ea: `0x6076b0`
- end: `0x608819`
- name: `Microsoft.SharePoint.Deployment.ListItemSerializer::SetObjectData`
- size: `4457`
- prototype: ``
- caller_count: `0`
- callee_count: `120`
- tags: `broker_com_uri`

## callees

- `0x1b7de0`
- `0x1b7e00`
- `0x273cc0`
- `0x343930`
- `0x344680`
- `0x344c40`
- `0x345490`
- `0x345a20`
- `0x345c30`
- `0x345f90`
- `0x347ec0`
- `0x3e9980`
- `0x3e99a0`
- `0x3e99f0`
- `0x491bd0`
- `0x4cc7c0`
- `0x5076d0`
- `0x50c610`
- `0x53b160`
- `0x53b180`
- `0x53be00`
- `0x53c770`
- `0x53e000`
- `0x53e0e0`
- `0x53e2d0`
- `0x53e830`
- `0x53f1c0`
- `0x540c50`
- `0x542e50`
- `0x543350`
- `0x572860`
- `0x572a50`
- `0x577060`
- `0x5c24f0`
- `0x5c3e40`
- `0x5c3eb0`
- `0x5c8f70`
- `0x5e7e70`
- `0x5e8060`
- `0x5e8070`
- `0x5e8080`
- `0x5e8090`
- `0x5e80a0`
- `0x5e81b0`
- `0x5e8230`
- `0x5f6650`
- `0x5fd700`
- `0x5fd990`
- `0x5fd9b0`
- `0x5fd9d0`

## string_xrefs

- `0x6078dd`: `Links`
- `0x60851c`: `Links`
- `0x608530`: `Links`
- `0x607b60`: `AccessDenied`
- `0x607b83`: `AccessDenied`
- `0x60871e`: `AccessDenied`
- `0x607da9`: `ThreadIndex`
- `0x607db7`: `ThreadIndex`
- `0x607dbd`: `ThreadIndex`
- `0x608156`: `ComplianceTag`
- `0x6081a1`: `ComplianceTag`
- `0x6083be`: `ComplianceTag`
- `0x608409`: `ComplianceTag`
- `0x6081c7`: `ComplianceFlags`
- `0x60842f`: `ComplianceFlags`
- `0x6081de`: `ComplianceTagUserId`
- `0x608446`: `ComplianceTagUserId`
- `0x6081fa`: `ComplianceTagWrittenTime`
- `0x608207`: `ComplianceTagWrittenTime`
- `0x608462`: `ComplianceTagWrittenTime`
- `0x60846f`: `ComplianceTagWrittenTime`
- `0x608591`: `Comments`
- `0x60826c`: `CommentFlags`
- `0x60827c`: `CommentFlags`
- `0x608298`: `CommentFlags`
- `0x607746`: `DisableIsCopyFlag`
- `0x607925`: `Job retried but one of these flags may not have been handled if the crash point is right after this listitem got committed. hasEventReceivers: {0}; hasAttachments: {1}; hasLinks: {2}; hasSharedWithData: {3}`
- `0x607ea5`: `SkipModerationForCopy`
- `0x608141`: `SetComplianceOnRootListItemMigration`
- `0x6083a9`: `SetComplianceOnRootListItemMigration`
- `0x608191`: `SkipLabelForCopyJob`
- `0x6083f9`: `SkipLabelForCopyJob`
- `0x6082ba`: `ListItemSerializer: Setting comment flags. Value = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6076b0  ldarg.0
0x6076b1  ldarg.2
0x6076b2  ldarga.s 3
0x6076b4  call     instance object [mscorlib]System.Runtime.Serialization.StreamingContext::get_Context()
0x6076b9  isinst   Microsoft.SharePoint.Deployment.ImportStreamingContext
0x6076be  call     instance void Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::InitializeImport(class [mscorlib]System.Runtime.Serialization.SerializationInfo info, class Microsoft.SharePoint.Deployment.ImportStreamingContext importContext)
0x6076c3  ldarg.0
0x6076c4  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x6076c9  callvirt instance bool Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_IsMigrationJob()
0x6076ce  brtrue.s loc_6076D3
0x6076d0  ldnull
0x6076d1  br.s     loc_607724
0x6076d3  ldstr    aListitemserial// "ListItemSerializer_SetObjectData"
0x6076d8  ldc.i4   0x8C4363
0x6076dd  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x6076e2  ldc.i4   0x8C4380
0x6076e7  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x6076ec  ldc.i4   0x8C4381
0x6076f1  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x6076f6  ldarg.0
0x6076f7  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x6076fc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_JobId()
0x607701  stloc.s  0x3F
0x607703  ldloca.s 0x3F
0x607705  constrained. [mscorlib]System.Guid
0x60770b  callvirt instance string [mscorlib]System.Object::ToString()
0x607710  ldarg.0
0x607711  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x607716  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_SubscriptionId()
0x60771b  ldnull
0x60771c  ldnull
0x60771d  ldc.i4.1
0x60771e  ldnull
0x60771f  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, string userLogin, valuetype [mscorlib]System.Guid siteSubscriptionID, [opt] class Microsoft.SharePoint.Diagnostics.PCIDBase startCounter, [opt] class Microsoft.SharePoint.Diagnostics.PCIDBase successCounter, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x607724  stloc.0
0x607725  ldarg.0
0x607726  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x60772b  callvirt instance valuetype Microsoft.SharePoint.Deployment.SPMigrationType Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_MigrationType()
0x607730  ldc.i4.1
0x607731  ceq
0x607733  stloc.1
0x607734  ldloc.1
0x607735  brfalse.s loc_607770
0x607737  ldstr    a7ad461c833dd49// "7ad461c8-33dd-49ed-9bdb-190b2329681a"
0x60773c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x607741  ldstr    a01232018// "01/23/2018"
0x607746  ldstr    aDisableiscopyf// "DisableIsCopyFlag"
0x60774b  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x607750  brtrue.s loc_607770
0x607752  ldarg.0
0x607753  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x607758  callvirt instance bool Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_IsMove()
0x60775d  brtrue.s loc_60776E
0x60775f  ldc.i4   0x3B6A
0x607764  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x607769  ldc.i4.0
0x60776a  ceq
0x60776c  br.s     loc_60776F
0x60776e  ldc.i4.0
0x60776f  stloc.1
0x607770  ldarg.0
0x607771  ldarg.1
0x607772  isinst   Microsoft.SharePoint.Deployment.DeploymentObject
0x607777  call     instance bool Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::HandleDelete(class Microsoft.SharePoint.Deployment.DeploymentObject deplObject)
0x60777c  brfalse.s loc_607790
0x60777e  ldloc.0
0x60777f  brfalse.s loc_607788
0x607781  ldloc.0
0x607782  ldnull
0x607783  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x607788  ldnull
0x607789  stloc.s  0x3E
0x60778b  leave    loc_608816
0x607790  ldloca.s 2
0x607792  ldarg.0
0x607793  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x607798  callvirt instance class [mscorlib]System.Runtime.Serialization.SerializationInfo Microsoft.SharePoint.Deployment.SerializationInfoHelper::get_Info()
0x60779d  ldstr    aDocid_0// "DocId"
0x6077a2  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x6077a7  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6077ac  ldarg.0
0x6077ad  call     instance class Microsoft.SharePoint.Deployment.ImportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportObjectManager()
0x6077b2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Deployment.SerializationInfoHelper> Microsoft.SharePoint.Deployment.ImportObjectManager::get_FileInfoCache()
0x6077b7  ldloc.2
0x6077b8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Deployment.SerializationInfoHelper>::ContainsKey(var<u1>)
0x6077bd  brfalse  loc_60785A
0x6077c2  ldarg.0
0x6077c3  call     instance class Microsoft.SharePoint.Deployment.ImportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportObjectManager()
0x6077c8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Deployment.SerializationInfoHelper> Microsoft.SharePoint.Deployment.ImportObjectManager::get_FileInfoCache()
0x6077cd  ldloc.2
0x6077ce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Deployment.SerializationInfoHelper>::get_Item(void)
0x6077d3  stloc.3
0x6077d4  ldarg.0
0x6077d5  ldc.i4.4
0x6077d6  ldloc.2
0x6077d7  ldloc.3
0x6077d8  callvirt instance class [mscorlib]System.Runtime.Serialization.SerializationInfo Microsoft.SharePoint.Deployment.SerializationInfoHelper::get_Info()
0x6077dd  ldstr    aUrl// "Url"
0x6077e2  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x6077e7  call     instance void Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::InitializeLoggerObject(valuetype Microsoft.SharePoint.Deployment.SPDeploymentObjectType objectType, valuetype [mscorlib]System.Guid originalId, string sourceUrl)
0x6077ec  ldloc.3
0x6077ed  ldstr    aFailuremessage// "FailureMessage"
0x6077f2  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x6077f7  brfalse.s loc_60785A
0x6077f9  ldstr    aImporteditemfa// "ImportedItemFailedOnExport"
0x6077fe  ldc.i4.1
0x6077ff  newarr   [mscorlib]System.Object
0x607804  stloc.s  0x40
0x607806  ldloc.s  0x40
0x607808  ldc.i4.0
0x607809  ldloc.3
0x60780a  callvirt instance class [mscorlib]System.Runtime.Serialization.SerializationInfo Microsoft.SharePoint.Deployment.SerializationInfoHelper::get_Info()
0x60780f  ldstr    aFailuremessage// "FailureMessage"
0x607814  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x607819  stelem.ref
0x60781a  ldloc.s  0x40
0x60781c  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x607821  stloc.s  4
0x607823  ldarg.0
0x607824  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x607829  callvirt instance class Microsoft.SharePoint.Deployment.DeploymentLogger Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_Logger()
0x60782e  ldc.i4.1
0x60782f  ldarg.0
0x607830  call     instance class Microsoft.SharePoint.Deployment.SPLoggerObject Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_LoggerObject()
0x607835  ldloc.s  4
0x607837  callvirt instance void Microsoft.SharePoint.Deployment.DeploymentLogger::Log(valuetype Microsoft.SharePoint.Deployment.DeploymentLogSeverity severity, class Microsoft.SharePoint.Deployment.SPLoggerObject loggerObject, string message)
0x60783c  ldloc.0
0x60783d  brfalse.s loc_607852
0x60783f  ldloc.0
0x607840  ldc.i4   0x101660B
0x607845  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x60784a  ldloc.s  4
0x60784c  ldnull
0x60784d  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x607852  ldnull
0x607853  stloc.s  0x3E
0x607855  leave    loc_608816
0x60785a  ldnull
0x60785b  stloc.s  5
0x60785d  ldarg.0
0x60785e  call     instance class Microsoft.SharePoint.Deployment.SPLoggerObject Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_LoggerObject()
0x607863  brtrue.s loc_607878
0x607865  ldarg.0
0x607866  ldc.i4.4
0x607867  ldloc.2
0x607868  ldarg.2
0x607869  ldstr    aFileurl_1// "FileUrl"
0x60786e  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x607873  call     instance void Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::InitializeLoggerObject(valuetype Microsoft.SharePoint.Deployment.SPDeploymentObjectType objectType, valuetype [mscorlib]System.Guid originalId, string sourceUrl)
0x607878  ldarg.2
0x607879  ldstr    aIntid// "IntId"
0x60787e  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x607883  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x607888  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x60788d  stloc.s  6
0x60788f  ldarg.0
0x607890  call     instance class Microsoft.SharePoint.Deployment.SPLoggerObject Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_LoggerObject()
0x607895  callvirt instance class Microsoft.SharePoint.Deployment.SPImportObject Microsoft.SharePoint.Deployment.SPLoggerObject::get_DeploymentObject()
0x60789a  stloc.s  7
0x60789c  ldloc.s  7
0x60789e  brfalse.s loc_6078B3
0x6078a0  ldloc.s  7
0x6078a2  ldloca.s 6
0x6078a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6078a9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6078ae  callvirt instance void Microsoft.SharePoint.Deployment.SPImportObject::set_ListItemSourceIntId(string value)
0x6078b3  ldarg.0
0x6078b4  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x6078b9  ldstr    aEventreceivers// "EventReceivers"
0x6078be  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x6078c3  stloc.s  8
0x6078c5  ldarg.0
0x6078c6  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x6078cb  ldstr    aAttachments// "Attachments"
0x6078d0  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x6078d5  stloc.s  9
0x6078d7  ldarg.0
0x6078d8  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x6078dd  ldstr    aLinks// "Links"
0x6078e2  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x6078e7  stloc.s  0xA
0x6078e9  ldarg.0
0x6078ea  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x6078ef  ldstr    aSharedwitheven// "SharedWithEvents"
0x6078f4  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x6078f9  stloc.s  0xB
0x6078fb  ldarg.0
0x6078fc  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x607901  callvirt instance int32 Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_TotalJobRetryCount()
0x607906  ldc.i4.0
0x607907  ble.s    loc_607965
0x607909  ldloc.s  8
0x60790b  brtrue.s loc_607919
0x60790d  ldloc.s  9
0x60790f  brtrue.s loc_607919
0x607911  ldloc.s  0xA
0x607913  brtrue.s loc_607919
0x607915  ldloc.s  0xB
0x607917  brfalse.s loc_607965
0x607919  ldc.i4   0x13D80D8
0x60791e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x607923  ldc.i4.s 0xA
0x607925  ldstr    aJobRetriedButO// "Job retried but one of these flags may "...
0x60792a  ldc.i4.4
0x60792b  newarr   [mscorlib]System.Object
0x607930  stloc.s  0x40
0x607932  ldloc.s  0x40
0x607934  ldc.i4.0
0x607935  ldloc.s  8
0x607937  box      [mscorlib]System.Boolean
0x60793c  stelem.ref
0x60793d  ldloc.s  0x40
0x60793f  ldc.i4.1
0x607940  ldloc.s  9
0x607942  box      [mscorlib]System.Boolean
0x607947  stelem.ref
0x607948  ldloc.s  0x40
0x60794a  ldc.i4.2
0x60794b  ldloc.s  0xA
0x60794d  box      [mscorlib]System.Boolean
0x607952  stelem.ref
0x607953  ldloc.s  0x40
0x607955  ldc.i4.3
0x607956  ldloc.s  0xB
0x607958  box      [mscorlib]System.Boolean
0x60795d  stelem.ref
0x60795e  ldloc.s  0x40
0x607960  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x607965  ldarg.0
0x607966  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x60796b  callvirt instance bool Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_InRetryMode()
0x607970  brfalse.s loc_6079C1
0x607972  ldarg.0
0x607973  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x607978  callvirt instance class Microsoft.SharePoint.Deployment.DeploymentLogger Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_Logger()
0x60797d  ldc.i4.7
0x60797e  ldarg.0
0x60797f  call     instance class Microsoft.SharePoint.Deployment.SPLoggerObject Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_LoggerObject()
0x607984  ldstr    aIgnoringitem// "IgnoringItem"
0x607989  ldc.i4.0
0x60798a  newarr   [mscorlib]System.Object
0x60798f  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x607994  callvirt instance void Microsoft.SharePoint.Deployment.DeploymentLogger::Log(valuetype Microsoft.SharePoint.Deployment.DeploymentLogSeverity severity, class Microsoft.SharePoint.Deployment.SPLoggerObject loggerObject, string message)
0x607999  ldc.i4   0x1322606
0x60799e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x6079a3  ldc.i4.s 0x32
0x6079a5  ldstr    aFastSkipItemAs// "Fast skip item as we're in resume mode."
0x6079aa  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x6079af  ldloc.0
0x6079b0  brfalse.s loc_6079B9
0x6079b2  ldloc.0
0x6079b3  ldnull
0x6079b4  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x6079b9  ldnull
0x6079ba  stloc.s  0x3E
0x6079bc  leave    loc_608816
0x6079c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6079c6  stloc.s  0xC
0x6079c8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6079cd  stloc.s  0xD
0x6079cf  ldnull
0x6079d0  stloc.s  0xE
0x6079d2  ldarg.0
0x6079d3  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x6079d8  call     valuetype Microsoft.SharePoint.SPFileSystemObjectType Microsoft.SharePoint.Deployment.ListItemSerializer::GetFileSystemObjectType(class Microsoft.SharePoint.Deployment.SerializationInfoHelper infoHelper)
0x6079dd  stloc.s  0xF
0x6079df  ldarg.0
0x6079e0  ldloca.s 0xC
0x6079e2  ldloca.s 0xD
0x6079e4  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Deployment.ListItemSerializer::GetParentWeb(valuetype [mscorlib]System.Guid& guidWeb, valuetype [mscorlib]System.Guid& guidList)
0x6079e9  stloc.s  0xE
0x6079eb  ldc.i4   0x231740B
0x6079f0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x6079f5  ldc.i4.s 0xF
0x6079f7  ldstr    aListitemserial_0// "ListItemSerializer.SetObjectData: guidW"...
0x6079fc  ldc.i4.2
0x6079fd  newarr   [mscorlib]System.Object
0x607a02  stloc.s  0x40
0x607a04  ldloc.s  0x40
0x607a06  ldc.i4.0
0x607a07  ldloc.s  0xC
0x607a09  box      [mscorlib]System.Guid
0x607a0e  stelem.ref
0x607a0f  ldloc.s  0x40
0x607a11  ldc.i4.1
0x607a12  ldloc.s  0xD
0x607a14  box      [mscorlib]System.Guid
0x607a19  stelem.ref
0x607a1a  ldloc.s  0x40
0x607a1c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x607a21  ldarg.0
0x607a22  ldloc.s  0xE
0x607a24  ldloc.s  0xD
0x607a26  call     instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.Deployment.ListItemSerializer::GetList(class Microsoft.SharePoint.SPWeb parentWeb, valuetype [mscorlib]System.Guid guidList)
0x607a2b  stloc.s  0x10
0x607a2d  ldarg.0
0x607a2e  call     instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportSettings()
0x607a33  callvirt instance class Microsoft.SharePoint.Deployment.DeploymentLogger Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_Logger()
0x607a38  ldc.i4.7
0x607a39  ldarg.0
  ... truncated ...
```
