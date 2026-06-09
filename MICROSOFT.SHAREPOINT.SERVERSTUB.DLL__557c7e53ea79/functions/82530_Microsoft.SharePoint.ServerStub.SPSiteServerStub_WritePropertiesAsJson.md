# Microsoft.SharePoint.ServerStub.SPSiteServerStub::WritePropertiesAsJson

- ea: `0x82530`
- end: `0x82e55`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::WritePropertiesAsJson`
- size: `2341`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x82530`

## string_xrefs

- `0x827c3`: `CurrentChangeToken`
- `0x827cf`: `CurrentChangeToken`
- `0x827da`: `CurrentChangeToken`
- `0x827f2`: `CurrentChangeToken`
- `0x82b29`: `ReadOnly`
- `0x82b35`: `ReadOnly`
- `0x82b40`: `ReadOnly`
- `0x82b58`: `ReadOnly`
- `0x82ab5`: `ResourcePath`
- `0x82ac1`: `ResourcePath`
- `0x82acc`: `ResourcePath`
- `0x82ae4`: `ResourcePath`
- `0x82c4b`: `ShareByLinkEnabled`
- `0x82c57`: `ShareByLinkEnabled`
- `0x82c62`: `ShareByLinkEnabled`
- `0x82c7a`: `ShareByLinkEnabled`
- `0x82545`: `AllowCreateDeclarativeWorkflow`
- `0x82551`: `AllowCreateDeclarativeWorkflow`
- `0x8255c`: `AllowCreateDeclarativeWorkflow`
- `0x82574`: `AllowCreateDeclarativeWorkflow`
- `0x825f3`: `AllowRevertFromTemplate`
- `0x825ff`: `AllowRevertFromTemplate`
- `0x8260a`: `AllowRevertFromTemplate`
- `0x82622`: `AllowRevertFromTemplate`
- `0x8262d`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x82639`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x82644`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x8265c`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x826a1`: `AllowSelfServiceUpgrade`
- `0x826ad`: `AllowSelfServiceUpgrade`
- `0x826b8`: `AllowSelfServiceUpgrade`
- `0x826d0`: `AllowSelfServiceUpgrade`
- `0x826db`: `AllowSelfServiceUpgradeEvaluation`
- `0x826e7`: `AllowSelfServiceUpgradeEvaluation`
- `0x826f2`: `AllowSelfServiceUpgradeEvaluation`
- `0x8270a`: `AllowSelfServiceUpgradeEvaluation`
- `0x82789`: `CompatibilityLevel`
- `0x82795`: `CompatibilityLevel`
- `0x827a0`: `CompatibilityLevel`
- `0x827b8`: `CompatibilityLevel`
- `0x82837`: `DisableCompanyWideSharingLinks`
- `0x82843`: `DisableCompanyWideSharingLinks`
- `0x8284e`: `DisableCompanyWideSharingLinks`
- `0x82866`: `DisableCompanyWideSharingLinks`
- `0x82aef`: `PrimaryUri`
- `0x82afb`: `PrimaryUri`
- `0x82b06`: `PrimaryUri`
- `0x82b1e`: `PrimaryUri`
- `0x82cf9`: `UIVersionConfigurationEnabled`
- `0x82d05`: `UIVersionConfigurationEnabled`
- `0x82d10`: `UIVersionConfigurationEnabled`
- `0x82d28`: `UIVersionConfigurationEnabled`
- `0x82d6d`: `UpgradeScheduled`
- `0x82d79`: `UpgradeScheduled`
- `0x82d84`: `UpgradeScheduled`
- `0x82d9c`: `UpgradeScheduled`
- `0x82da7`: `UpgradeScheduledDate`
- `0x82db3`: `UpgradeScheduledDate`
- `0x82dbe`: `UpgradeScheduledDate`
- `0x82dd6`: `UpgradeScheduledDate`

## pseudocode

```c

```

## disassembly

```asm
0x82530  ldarg.2
0x82531  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0x82536  stloc.0
0x82537  ldloc.0
0x82538  brtrue.s loc_8253B
0x8253a  ret
0x8253b  ldarg.0
0x8253c  ldarg.1
0x8253d  ldarg.2
0x8253e  ldarg.3
0x8253f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82544  ldarg.0
0x82545  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x8254a  ldarg.3
0x8254b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82550  ldarg.1
0x82551  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x82556  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8255b  ldarg.3
0x8255c  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x82561  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x82566  ldarg.1
0x82567  ldloc.0
0x82568  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowCreateDeclarativeWorkflow()
0x8256d  ldarg.3
0x8256e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82573  ldarg.3
0x82574  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x82579  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8257e  ldarg.0
0x8257f  ldstr    aAllowdesigner// "AllowDesigner"
0x82584  ldarg.3
0x82585  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8258a  ldarg.1
0x8258b  ldstr    aAllowdesigner// "AllowDesigner"
0x82590  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x82595  ldarg.3
0x82596  ldstr    aAllowdesigner// "AllowDesigner"
0x8259b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x825a0  ldarg.1
0x825a1  ldloc.0
0x825a2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowDesigner()
0x825a7  ldarg.3
0x825a8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x825ad  ldarg.3
0x825ae  ldstr    aAllowdesigner// "AllowDesigner"
0x825b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x825b8  ldarg.0
0x825b9  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x825be  ldarg.3
0x825bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x825c4  ldarg.1
0x825c5  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x825ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x825cf  ldarg.3
0x825d0  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x825d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x825da  ldarg.1
0x825db  ldloc.0
0x825dc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowMasterPageEditing()
0x825e1  ldarg.3
0x825e2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x825e7  ldarg.3
0x825e8  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x825ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x825f2  ldarg.0
0x825f3  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x825f8  ldarg.3
0x825f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x825fe  ldarg.1
0x825ff  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x82604  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x82609  ldarg.3
0x8260a  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x8260f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x82614  ldarg.1
0x82615  ldloc.0
0x82616  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowRevertFromTemplate()
0x8261b  ldarg.3
0x8261c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82621  ldarg.3
0x82622  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x82627  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8262c  ldarg.0
0x8262d  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x82632  ldarg.3
0x82633  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82638  ldarg.1
0x82639  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x8263e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x82643  ldarg.3
0x82644  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x82649  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8264e  ldarg.1
0x8264f  ldloc.0
0x82650  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowSaveDeclarativeWorkflowAsTemplate()
0x82655  ldarg.3
0x82656  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8265b  ldarg.3
0x8265c  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x82661  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x82666  ldarg.0
0x82667  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x8266c  ldarg.3
0x8266d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82672  ldarg.1
0x82673  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x82678  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8267d  ldarg.3
0x8267e  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x82683  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x82688  ldarg.1
0x82689  ldloc.0
0x8268a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowSavePublishDeclarativeWorkflow()
0x8268f  ldarg.3
0x82690  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82695  ldarg.3
0x82696  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x8269b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x826a0  ldarg.0
0x826a1  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x826a6  ldarg.3
0x826a7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x826ac  ldarg.1
0x826ad  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x826b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x826b7  ldarg.3
0x826b8  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x826bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x826c2  ldarg.1
0x826c3  ldloc.0
0x826c4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowSelfServiceUpgrade()
0x826c9  ldarg.3
0x826ca  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x826cf  ldarg.3
0x826d0  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x826d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x826da  ldarg.0
0x826db  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x826e0  ldarg.3
0x826e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x826e6  ldarg.1
0x826e7  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x826ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x826f1  ldarg.3
0x826f2  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x826f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x826fc  ldarg.1
0x826fd  ldloc.0
0x826fe  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowSelfServiceUpgradeEvaluation()
0x82703  ldarg.3
0x82704  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82709  ldarg.3
0x8270a  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x8270f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x82714  ldarg.0
0x82715  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x8271a  ldarg.3
0x8271b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82720  ldarg.1
0x82721  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x82726  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8272b  ldarg.3
0x8272c  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x82731  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x82736  ldarg.1
0x82737  ldloc.0
0x82738  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AuditLogTrimmingRetention()
0x8273d  ldarg.3
0x8273e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82743  ldarg.3
0x82744  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x82749  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8274e  ldarg.0
0x8274f  ldstr    aClassification// "Classification"
0x82754  ldarg.3
0x82755  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8275a  ldarg.1
0x8275b  ldstr    aClassification// "Classification"
0x82760  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x82765  ldarg.3
0x82766  ldstr    aClassification// "Classification"
0x8276b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x82770  ldarg.1
0x82771  ldloc.0
0x82772  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Classification()
0x82777  ldarg.3
0x82778  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8277d  ldarg.3
0x8277e  ldstr    aClassification// "Classification"
0x82783  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x82788  ldarg.0
0x82789  ldstr    aCompatibilityl_0// "CompatibilityLevel"
0x8278e  ldarg.3
0x8278f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82794  ldarg.1
0x82795  ldstr    aCompatibilityl_0// "CompatibilityLevel"
0x8279a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8279f  ldarg.3
0x827a0  ldstr    aCompatibilityl_0// "CompatibilityLevel"
0x827a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x827aa  ldarg.1
0x827ab  ldloc.0
0x827ac  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_CompatibilityLevel()
0x827b1  ldarg.3
0x827b2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x827b7  ldarg.3
0x827b8  ldstr    aCompatibilityl_0// "CompatibilityLevel"
0x827bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x827c2  ldarg.0
0x827c3  ldstr    aCurrentchanget// "CurrentChangeToken"
0x827c8  ldarg.3
0x827c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x827ce  ldarg.1
0x827cf  ldstr    aCurrentchanget// "CurrentChangeToken"
0x827d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x827d9  ldarg.3
0x827da  ldstr    aCurrentchanget// "CurrentChangeToken"
0x827df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x827e4  ldarg.1
0x827e5  ldloc.0
0x827e6  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_CurrentChangeToken()
0x827eb  ldarg.3
0x827ec  call     T0x2B000024
0x827f1  ldarg.3
0x827f2  ldstr    aCurrentchanget// "CurrentChangeToken"
0x827f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x827fc  ldarg.0
0x827fd  ldstr    aDisableappview// "DisableAppViews"
0x82802  ldarg.3
0x82803  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82808  ldarg.1
0x82809  ldstr    aDisableappview// "DisableAppViews"
0x8280e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x82813  ldarg.3
0x82814  ldstr    aDisableappview// "DisableAppViews"
0x82819  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8281e  ldarg.1
0x8281f  ldloc.0
0x82820  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_DisableAppViews()
0x82825  ldarg.3
0x82826  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8282b  ldarg.3
0x8282c  ldstr    aDisableappview// "DisableAppViews"
0x82831  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x82836  ldarg.0
0x82837  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x8283c  ldarg.3
0x8283d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82842  ldarg.1
0x82843  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x82848  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8284d  ldarg.3
0x8284e  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x82853  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x82858  ldarg.1
0x82859  ldloc.0
0x8285a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_DisableCompanyWideSharingLinks()
0x8285f  ldarg.3
0x82860  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x82865  ldarg.3
0x82866  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x8286b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x82870  ldarg.0
0x82871  ldstr    aDisableflows// "DisableFlows"
0x82876  ldarg.3
0x82877  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8287c  ldarg.1
0x8287d  ldstr    aDisableflows// "DisableFlows"
0x82882  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x82887  ldarg.3
0x82888  ldstr    aDisableflows// "DisableFlows"
0x8288d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x82892  ldarg.1
0x82893  ldloc.0
0x82894  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_DisableFlows()
0x82899  ldarg.3
0x8289a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8289f  ldarg.3
0x828a0  ldstr    aDisableflows// "DisableFlows"
0x828a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x828aa  ldarg.0
0x828ab  ldstr    aExternalsharin// "ExternalSharingTipsEnabled"
0x828b0  ldarg.3
0x828b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x828b6  ldarg.1
0x828b7  ldstr    aExternalsharin// "ExternalSharingTipsEnabled"
0x828bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x828c1  ldarg.3
0x828c2  ldstr    aExternalsharin// "ExternalSharingTipsEnabled"
0x828c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x828cc  ldarg.1
0x828cd  ldloc.0
0x828ce  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ExternalSharingTipsEnabled()
0x828d3  ldarg.3
0x828d4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x828d9  ldarg.3
0x828da  ldstr    aExternalsharin// "ExternalSharingTipsEnabled"
0x828df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x828e4  ldarg.0
  ... truncated ...
```
