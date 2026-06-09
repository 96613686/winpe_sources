# Microsoft.SharePoint.Deployment.WebSerializer::SetObjectData

- ea: `0x627210`
- end: `0x62833e`
- name: `Microsoft.SharePoint.Deployment.WebSerializer::SetObjectData`
- size: `4398`
- prototype: ``
- caller_count: `0`
- callee_count: `126`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1b7de0`
- `0x26e5b0`
- `0x26fa60`
- `0x3428d0`
- `0x3428f0`
- `0x342900`
- `0x525e00`
- `0x526c70`
- `0x576070`
- `0x5760b0`
- `0x5761a0`
- `0x5761c0`
- `0x5761e0`
- `0x576200`
- `0x576250`
- `0x576270`
- `0x576290`
- `0x5762d0`
- `0x5762f0`
- `0x576320`
- `0x5765e0`
- `0x577060`
- `0x5adb90`
- `0x5c0760`
- `0x5c0e70`
- `0x5c0f80`
- `0x5c11c0`
- `0x5c1590`
- `0x5c1620`
- `0x5c1670`
- `0x5c24f0`
- `0x5c2a00`
- `0x5c2ce0`
- `0x5c2db0`
- `0x5c2ed0`
- `0x5c2fd0`
- `0x5c3040`
- `0x5c3080`
- `0x5c30e0`
- `0x5c33c0`
- `0x5c3750`
- `0x5c3bd0`
- `0x5c3c90`
- `0x5c3ce0`
- `0x5c3da0`
- `0x5c3db0`
- `0x5c3e90`
- `0x5c3f30`
- `0x5c43f0`
- `0x5c4470`

## string_xrefs

- `0x6272e3`: `WebTemplate`
- `0x6272f6`: `WebTemplate`
- `0x6281b4`: `WebTemplate`
- `0x6281ca`: `WebTemplate`
- `0x62730c`: `Configuration`
- `0x62731f`: `Configuration`
- `0x628268`: `Configuration`
- `0x62827b`: `Configuration`
- `0x627cba`: `Created`
- `0x627980`: `HasPendingWebTemplateExtension`
- `0x627993`: `HasPendingWebTemplateExtension`
- `0x627b7f`: `CommentsOnSitePagesDisabled`
- `0x627a6a`: `HideSiteContentsLink`
- `0x627e39`: `RequestAccessEmail`
- `0x627c9a`: `SetupPathUser`
- `0x627a3f`: `CacheAllSchema`
- `0x627d8e`: `SecurityProvider`
- `0x627f73`: `OverwriteTranslationsOnChange`
- `0x6281f0`: `CentralAdminTemplateMisMatch`
- `0x628232`: `CentralAdminTemplateMisMatch`

## pseudocode

```c

```

## disassembly

```asm
0x627210  ldarg.0
0x627211  ldarg.2
0x627212  ldarga.s 3
0x627214  call     instance object [mscorlib]System.Runtime.Serialization.StreamingContext::get_Context()
0x627219  isinst   Microsoft.SharePoint.Deployment.ImportStreamingContext
0x62721e  call     instance void Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::InitializeImport(class [mscorlib]System.Runtime.Serialization.SerializationInfo info, class Microsoft.SharePoint.Deployment.ImportStreamingContext importContext)
0x627223  ldarg.1
0x627224  isinst   Microsoft.SharePoint.Deployment.DeploymentObject
0x627229  stloc.0
0x62722a  ldarg.0
0x62722b  ldloc.0
0x62722c  call     instance bool Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::HandleDelete(class Microsoft.SharePoint.Deployment.DeploymentObject deplObject)
0x627231  brfalse.s loc_627235
0x627233  ldnull
0x627234  ret
0x627235  ldloc.0
0x627236  brfalse.s loc_62725B
0x627238  ldloc.0
0x627239  callvirt instance bool Microsoft.SharePoint.Deployment.DeploymentObject::get_IsSiteRename()
0x62723e  brfalse.s loc_62725B
0x627240  ldarg.0
0x627241  ldc.i4.1
0x627242  ldloc.0
0x627243  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_Id()
0x627248  ldloc.0
0x627249  callvirt instance string Microsoft.SharePoint.Deployment.DeploymentObject::get_Url()
0x62724e  call     instance void Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::InitializeLoggerObject(valuetype Microsoft.SharePoint.Deployment.SPDeploymentObjectType objectType, valuetype [mscorlib]System.Guid originalId, string sourceUrl)
0x627253  ldarg.0
0x627254  ldloc.0
0x627255  call     instance object Microsoft.SharePoint.Deployment.WebSerializer::RenameObject(class Microsoft.SharePoint.Deployment.DeploymentObject deployObject)
0x62725a  ret
0x62725b  ldarg.0
0x62725c  call     instance class Microsoft.SharePoint.Deployment.ImportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportObjectManager()
0x627261  stloc.1
0x627262  ldnull
0x627263  stloc.2
0x627264  ldc.i4.0
0x627265  stloc.3
0x627266  ldc.i4.0
0x627267  stloc.s  4
0x627269  ldc.i4.0
0x62726a  stloc.s  5
0x62726c  ldc.i4.0
0x62726d  stloc.s  6
0x62726f  ldnull
0x627270  stloc.s  7
0x627272  ldnull
0x627273  stloc.s  8
0x627275  ldnull
0x627276  stloc.s  9
0x627278  ldnull
0x627279  stloc.s  0xA
0x62727b  ldnull
0x62727c  stloc.s  0xB
0x62727e  ldnull
0x62727f  stloc.s  0xC
0x627281  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x627286  stloc.s  0xD
0x627288  ldarg.0
0x627289  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x62728e  stloc.s  0xE
0x627290  ldarg.2
0x627291  ldloca.s 5
0x627293  ldloca.s 6
0x627295  call     void Microsoft.SharePoint.Deployment.CommonInfo::GetFlags(class [mscorlib]System.Runtime.Serialization.SerializationInfo info, bool& isPreSubElement, bool& isPostSubElement)
0x62729a  ldloc.s  5
0x62729c  brfalse  loc_6273A8
0x6272a1  ldarg.0
0x6272a2  ldc.i4.1
0x6272a3  ldstr    aServerrelative_2// "ServerRelativeUrl"
0x6272a8  call     instance void Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::InitializeLoggerObject(valuetype Microsoft.SharePoint.Deployment.SPDeploymentObjectType objectType, string attributeName)
0x6272ad  ldarg.0
0x6272ae  ldloc.s  0xE
0x6272b0  ldarg.0
0x6272b1  call     instance class Microsoft.SharePoint.Deployment.ImportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportObjectManager()
0x6272b6  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Deployment.WebSerializer::GetWeb(class Microsoft.SharePoint.Deployment.SerializationInfoHelper infoHelper, class Microsoft.SharePoint.Deployment.ImportObjectManager objectManager)
0x6272bb  stloc.2
0x6272bc  ldarg.0
0x6272bd  call     instance class Microsoft.SharePoint.Deployment.ImportStreamingContext Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ImportContext()
0x6272c2  ldnull
0x6272c3  ldloc.2
0x6272c4  call     bool Microsoft.SharePoint.Deployment.SecurityCheck::OnWebImport(class Microsoft.SharePoint.Deployment.ImportStreamingContext context, class Microsoft.SharePoint.SPWeb parentWeb, class Microsoft.SharePoint.SPWeb currentWeb)
0x6272c9  brtrue.s loc_6272CD
0x6272cb  ldnull
0x6272cc  ret
0x6272cd  ldloc.2
0x6272ce  brtrue.s loc_6272E1
0x6272d0  ldarg.0
0x6272d1  ldloc.s  0xE
0x6272d3  ldloc.1
0x6272d4  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Deployment.WebSerializer::CreateWeb(class Microsoft.SharePoint.Deployment.SerializationInfoHelper infoHelper, class Microsoft.SharePoint.Deployment.ImportObjectManager objectManager)
0x6272d9  stloc.2
0x6272da  ldc.i4.1
0x6272db  stloc.3
0x6272dc  br       loc_6273AF
0x6272e1  ldloc.s  0xE
0x6272e3  ldstr    aWebtemplate// "WebTemplate"
0x6272e8  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x6272ed  brfalse.s loc_627349
0x6272ef  ldloc.s  0xE
0x6272f1  callvirt instance class [mscorlib]System.Runtime.Serialization.SerializationInfo Microsoft.SharePoint.Deployment.SerializationInfoHelper::get_Info()
0x6272f6  ldstr    aWebtemplate// "WebTemplate"
0x6272fb  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x627300  stloc.s  0xF
0x627302  ldloc.2
0x627303  callvirt instance int16 Microsoft.SharePoint.SPWeb::get_Configuration()
0x627308  stloc.s  0x10
0x62730a  ldloc.s  0xE
0x62730c  ldstr    aConfiguration_1// "Configuration"
0x627311  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x627316  brfalse.s loc_62732B
0x627318  ldloc.s  0xE
0x62731a  callvirt instance class [mscorlib]System.Runtime.Serialization.SerializationInfo Microsoft.SharePoint.Deployment.SerializationInfoHelper::get_Info()
0x62731f  ldstr    aConfiguration_1// "Configuration"
0x627324  callvirt instance int32 [mscorlib]System.Runtime.Serialization.SerializationInfo::GetInt32(string)
0x627329  stloc.s  0x10
0x62732b  ldloc.s  0xF
0x62732d  ldstr    asc_C80842// "#"
0x627332  ldloc.s  0x10
0x627334  box      [mscorlib]System.Int32
0x627339  call     string [mscorlib]System.String::Concat(object, object, object)
0x62733e  ldloc.2
0x62733f  callvirt instance string Microsoft.SharePoint.SPWeb::get_WebTemplateConfiguration()
0x627344  call     void Microsoft.SharePoint.Deployment.WebSerializer::IsWebTemplateCompatible(string sourceWebTemplateName, string destinationWebTemplateName)
0x627349  ldloc.s  0xE
0x62734b  ldstr    aLanguage// "Language"
0x627350  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x627355  brfalse.s loc_6273AF
0x627357  ldloc.s  0xE
0x627359  callvirt instance class [mscorlib]System.Runtime.Serialization.SerializationInfo Microsoft.SharePoint.Deployment.SerializationInfoHelper::get_Info()
0x62735e  ldstr    aLanguage// "Language"
0x627363  callvirt instance unsigned int32 [mscorlib]System.Runtime.Serialization.SerializationInfo::GetUInt32(string)
0x627368  stloc.s  0x11
0x62736a  ldloc.2
0x62736b  callvirt instance unsigned int32 Microsoft.SharePoint.SPWeb::get_Language()
0x627370  ldloc.s  0x11
0x627372  beq.s    loc_6273AF
0x627374  ldstr    aLanguagemismat// "LanguageMisMatch"
0x627379  ldc.i4.2
0x62737a  newarr   [mscorlib]System.Object
0x62737f  stloc.s  0x2E
0x627381  ldloc.s  0x2E
0x627383  ldc.i4.0
0x627384  ldloc.s  0x11
0x627386  box      [mscorlib]System.UInt32
0x62738b  stelem.ref
0x62738c  ldloc.s  0x2E
0x62738e  ldc.i4.1
0x62738f  ldloc.2
0x627390  callvirt instance unsigned int32 Microsoft.SharePoint.SPWeb::get_Language()
0x627395  box      [mscorlib]System.UInt32
0x62739a  stelem.ref
0x62739b  ldloc.s  0x2E
0x62739d  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x6273a2  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x6273a7  throw
0x6273a8  ldarg.1
0x6273a9  castclass Microsoft.SharePoint.SPWeb
0x6273ae  stloc.2
0x6273af  ldloc.2
0x6273b0  brtrue.s loc_6273B4
0x6273b2  ldnull
0x6273b3  ret
0x6273b4  ldarg.2
0x6273b5  ldstr    aServerrelative_2// "ServerRelativeUrl"
0x6273ba  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x6273bf  stloc.s  0x12
0x6273c1  ldloc.s  5
0x6273c3  brfalse  loc_6280A9
0x6273c8  ldloc.1
0x6273c9  callvirt instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.ImportObjectManager::get_ImportSettings()
0x6273ce  callvirt instance class Microsoft.SharePoint.Deployment.DeploymentLogger Microsoft.SharePoint.Deployment.SPDeploymentSettings::get_Logger()
0x6273d3  ldc.i4.7
0x6273d4  ldarg.0
0x6273d5  call     instance class Microsoft.SharePoint.Deployment.SPLoggerObject Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_LoggerObject()
0x6273da  ldstr    aWebimportexpor// "WebImportExport"
0x6273df  ldc.i4.2
0x6273e0  newarr   [mscorlib]System.Object
0x6273e5  stloc.s  0x2F
0x6273e7  ldloc.s  0x2F
0x6273e9  ldc.i4.0
0x6273ea  ldstr    aImporting// "Importing"
0x6273ef  ldc.i4.0
0x6273f0  newarr   [mscorlib]System.Object
0x6273f5  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x6273fa  stelem.ref
0x6273fb  ldloc.s  0x2F
0x6273fd  ldc.i4.1
0x6273fe  ldloc.2
0x6273ff  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x627404  stelem.ref
0x627405  ldloc.s  0x2F
0x627407  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x62740c  callvirt instance void Microsoft.SharePoint.Deployment.DeploymentLogger::Log(valuetype Microsoft.SharePoint.Deployment.DeploymentLogSeverity severity, class Microsoft.SharePoint.Deployment.SPLoggerObject loggerObject, string message)
0x627411  ldloc.3
0x627412  brtrue.s loc_627443
0x627414  ldloc.1
0x627415  callvirt instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.ImportObjectManager::get_ImportSettings()
0x62741a  callvirt instance bool Microsoft.SharePoint.Deployment.SPImportSettings::get_RetainObjectIdentity()
0x62741f  brfalse.s loc_627443
0x627421  ldloc.1
0x627422  ldloc.s  0x12
0x627424  callvirt instance string Microsoft.SharePoint.Deployment.ImportObjectManager::ConvertToDestinationServerRelativeUrl(string sourceUrl)
0x627429  stloc.s  0x13
0x62742b  ldloc.2
0x62742c  callvirt instance string Microsoft.SharePoint.SPWeb::get_ServerRelativeUrl()
0x627431  ldloc.s  0x13
0x627433  ldc.i4.5
0x627434  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x627439  brtrue.s loc_627443
0x62743b  ldloc.2
0x62743c  ldloc.s  0x13
0x62743e  callvirt instance void Microsoft.SharePoint.SPWeb::set_ServerRelativeUrl(string value)
0x627443  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x627448  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x62744d  stloc.s  0x14
0x62744f  ldloc.s  0xE
0x627451  ldstr    aLocale_0// "Locale"
0x627456  callvirt instance bool Microsoft.SharePoint.Deployment.SerializationInfoHelper::Contains(string entryName)
0x62745b  brfalse.s loc_627490
0x62745d  ldtoken  [mscorlib]System.Globalization.CultureInfo
0x627462  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x627467  call     class [System]System.ComponentModel.TypeConverter [System]System.ComponentModel.TypeDescriptor::GetConverter(class [mscorlib]System.Type)
0x62746c  ldarg.2
0x62746d  ldstr    aLocale_0// "Locale"
0x627472  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x627477  callvirt instance object [System]System.ComponentModel.TypeConverter::ConvertFrom(object)
0x62747c  castclass [mscorlib]System.Globalization.CultureInfo
0x627481  stloc.s  0x14
0x627483  leave.s  loc_627490
0x627485  pop
0x627486  ldloc.2
0x627487  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.SPWeb::get_Locale()
0x62748c  stloc.s  0x14
0x62748e  leave.s  loc_627490
0x627490  ldarg.2
0x627491  callvirt instance class [mscorlib]System.Runtime.Serialization.SerializationInfoEnumerator [mscorlib]System.Runtime.Serialization.SerializationInfo::GetEnumerator()
0x627496  stloc.s  0x30
0x627498  br       loc_627FE5
0x62749d  ldloc.s  0x30
0x62749f  callvirt instance valuetype [mscorlib]System.Runtime.Serialization.SerializationEntry [mscorlib]System.Runtime.Serialization.SerializationInfoEnumerator::get_Current()
0x6274a4  stloc.s  0x15
0x6274a6  ldloca.s 0x15
0x6274a8  call     instance string [mscorlib]System.Runtime.Serialization.SerializationEntry::get_Name()
0x6274ad  ldstr    aName_0// "Name"
0x6274b2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6274b7  brfalse.s loc_6274E4
0x6274b9  ldloc.2
0x6274ba  callvirt instance bool Microsoft.SharePoint.SPWeb::get_IsRootWeb()
0x6274bf  brtrue.s loc_6274E4
0x6274c1  ldloc.1
0x6274c2  callvirt instance class Microsoft.SharePoint.Deployment.SPImportSettings Microsoft.SharePoint.Deployment.ImportObjectManager::get_ImportSettings()
0x6274c7  callvirt instance bool Microsoft.SharePoint.Deployment.SPImportSettings::get_RetainObjectIdentity()
0x6274cc  brfalse.s loc_6274E4
0x6274ce  ldloc.2
0x6274cf  ldarg.2
0x6274d0  ldstr    aName_0// "Name"
0x6274d5  callvirt instance string [mscorlib]System.Runtime.Serialization.SerializationInfo::GetString(string)
0x6274da  callvirt instance void Microsoft.SharePoint.SPWeb::set_Name(string value)
0x6274df  br       loc_627FE5
0x6274e4  ldloca.s 0x15
0x6274e6  call     instance string [mscorlib]System.Runtime.Serialization.SerializationEntry::get_Name()
0x6274eb  ldstr    aDescription// "Description"
0x6274f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6274f5  brfalse.s loc_627522
0x6274f7  ldloc.2
0x6274f8  newobj   instance void Microsoft.SharePoint.Utilities.ThreadCultureScope::.ctor(class Microsoft.SharePoint.SPWeb web)
0x6274fd  stloc.s  0x16
0x6274ff  ldloc.2
0x627500  ldloca.s 0x15
0x627502  call     instance object [mscorlib]System.Runtime.Serialization.SerializationEntry::get_Value()
0x627507  castclass [mscorlib]System.String
0x62750c  callvirt instance void Microsoft.SharePoint.SPWeb::set_Description(string value)
0x627511  leave    loc_627FE5
0x627516  ldloc.s  0x16
0x627518  brfalse.s loc_627521
0x62751a  ldloc.s  0x16
0x62751c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x627521  endfinally
0x627522  ldloca.s 0x15
0x627524  call     instance string [mscorlib]System.Runtime.Serialization.SerializationEntry::get_Name()
0x627529  ldstr    aLocale_0// "Locale"
0x62752e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x627533  brfalse.s loc_627548
0x627535  ldloc.2
0x627536  ldloc.s  0x14
0x627538  callvirt instance void Microsoft.SharePoint.SPWeb::set_Locale(class [mscorlib]System.Globalization.CultureInfo value)
0x62753d  leave    loc_627FE5
0x627542  pop
0x627543  leave    loc_627FE5
0x627548  ldloca.s 0x15
0x62754a  call     instance string [mscorlib]System.Runtime.Serialization.SerializationEntry::get_Name()
0x62754f  ldstr    aCurrencylocale_1// "CurrencyLocaleId"
0x627554  call     bool [mscorlib]System.String::op_Equality(string, string)
0x627559  brfalse.s loc_627573
0x62755b  ldloc.2
0x62755c  ldarg.2
0x62755d  ldloca.s 0x15
0x62755f  call     instance string [mscorlib]System.Runtime.Serialization.SerializationEntry::get_Name()
0x627564  callvirt instance int32 [mscorlib]System.Runtime.Serialization.SerializationInfo::GetInt32(string)
  ... truncated ...
```
