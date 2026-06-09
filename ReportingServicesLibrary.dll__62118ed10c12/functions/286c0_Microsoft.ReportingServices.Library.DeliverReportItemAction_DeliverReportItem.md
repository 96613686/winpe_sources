# Microsoft.ReportingServices.Library.DeliverReportItemAction::DeliverReportItem

- ea: `0x286c0`
- end: `0x2882f`
- name: `Microsoft.ReportingServices.Library.DeliverReportItemAction::DeliverReportItem`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x3e450`

## callees

- `0x19890`
- `0x1e270`
- `0x1e370`
- `0x1e3e0`
- `0x1e460`
- `0x22e20`
- `0x22e40`
- `0x233b0`
- `0x286c0`
- `0x28830`
- `0x28a20`
- `0x28ac0`
- `0x43920`
- `0x5bb20`
- `0x5e0d0`
- `0x5e0e0`
- `0x5ea50`
- `0x71340`

## string_xrefs

- `0x286d1`: `ExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x286c0  ldarg.1
0x286c1  brtrue.s loc_286CE
0x286c3  ldstr    aFormat_0// "Format"
0x286c8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x286cd  throw
0x286ce  ldarg.3
0x286cf  brtrue.s loc_286DC
0x286d1  ldstr    aExtensionsetti_0// "ExtensionSettings"
0x286d6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x286db  throw
0x286dc  nop
0x286dd  ldarg.0
0x286de  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x286e3  callvirt instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x286e8  ldarg.0
0x286e9  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x286ee  callvirt instance bool Microsoft.ReportingServices.Library.RSService::IsSchedulerRunning()
0x286f3  brtrue.s loc_286FB
0x286f5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.SchedulerNotRespondingPreventsPinningException::.ctor()
0x286fa  throw
0x286fb  ldarg.0
0x286fc  ldfld    class Microsoft.ReportingServices.Library.SessionfulClientRequest Microsoft.ReportingServices.Library.DeliverReportItemAction::m_session
0x28701  ldarg.0
0x28702  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x28707  call     class Microsoft.ReportingServices.Library.SessionStarterAction Microsoft.ReportingServices.Library.SessionStarterAction::CreateExisting(class Microsoft.ReportingServices.Library.SessionfulClientRequest session, class Microsoft.ReportingServices.Library.RSService service)
0x2870c  pop
0x2870d  ldc.i4.0
0x2870e  stloc.0
0x2870f  ldarg.0
0x28710  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x28715  ldarg.0
0x28716  ldfld    class Microsoft.ReportingServices.Library.SessionfulClientRequest Microsoft.ReportingServices.Library.DeliverReportItemAction::m_session
0x2871b  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x28720  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x28725  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ReportDefinitionPath()
0x2872a  ldstr    aReport_0// "report"
0x2872f  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath, string)
0x28734  stloc.1
0x28735  ldarg.0
0x28736  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x2873b  callvirt instance class Microsoft.ReportingServices.Library.CatalogItemFactory Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0x28740  ldloc.1
0x28741  ldc.i4.1
0x28742  callvirt instance class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, bool doSync)
0x28747  stloc.2
0x28748  ldarg.0
0x28749  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.DeliverReportItemAction::ConstructParameters()
0x2874e  stloc.3
0x2874f  ldarg.3
0x28750  ldfld    string Microsoft.ReportingServices.Library.Soap.ExtensionSettings::Extension
0x28755  ldstr    aDelivery// "Delivery"
0x2875a  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string, string)
0x2875f  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension::get_LocalizedName()
0x28764  ldstr    aPowerBiDashboa// "Power BI Dashboard"
0x28769  ldc.i4.5
0x2876a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2876f  brtrue.s loc_287C8
0x28771  ldarg.0
0x28772  ldarg.1
0x28773  ldarg.3
0x28774  ldloc.1
0x28775  ldloc.3
0x28776  call     instance string Microsoft.ReportingServices.Library.DeliverReportItemAction::DeliverToPbi(string Format, class Microsoft.ReportingServices.Library.Soap.ExtensionSettings ExtensionSettings, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x2877b  stloc.s  5
0x2877d  ldloc.s  5
0x2877f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x28784  brtrue.s loc_287C6
0x28786  newobj   instance void Microsoft.ReportingServices.Library.Soap.ParameterValue::.ctor()
0x2878b  stloc.s  6
0x2878d  ldloc.s  6
0x2878f  ldstr    aTileid// "TileID"
0x28794  stfld    string Microsoft.ReportingServices.Library.Soap.ParameterValue::Name
0x28799  ldloc.s  6
0x2879b  ldloc.s  5
0x2879d  stfld    string Microsoft.ReportingServices.Library.Soap.ParameterValue::Value
0x287a2  ldarg.3
0x287a3  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x287a8  ldlen
0x287a9  conv.i4
0x287aa  stloc.s  7
0x287ac  ldarg.3
0x287ad  ldflda   class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x287b2  ldloc.s  7
0x287b4  ldc.i4.1
0x287b5  add
0x287b6  call     T0x2B00001B
0x287bb  ldarg.3
0x287bc  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x287c1  ldloc.s  7
0x287c3  ldloc.s  6
0x287c5  stelem.ref
0x287c6  ldc.i4.1
0x287c7  stloc.0
0x287c8  ldarg.0
0x287c9  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x287ce  callvirt instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x287d3  ldarg.0
0x287d4  ldarg.0
0x287d5  ldfld    class Microsoft.ReportingServices.Library.SessionfulClientRequest Microsoft.ReportingServices.Library.DeliverReportItemAction::m_session
0x287da  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x287df  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x287e4  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x287e9  ldloc.2
0x287ea  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.CatalogItem::get_ItemID()
0x287ef  ldarg.s  5
0x287f1  ldarg.s  6
0x287f3  ldarg.3
0x287f4  ldarg.s  4
0x287f6  ldloc.3
0x287f7  ldloc.2
0x287f8  castclass Microsoft.ReportingServices.Library.BaseReportCatalogItem
0x287fd  callvirt instance unsigned int8[] Microsoft.ReportingServices.Library.CatalogItem::get_SecurityDescriptor()
0x28802  call     instance string Microsoft.ReportingServices.Library.DeliverReportItemAction::CreateRefreshSubscription(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath, valuetype [mscorlib]System.Guid itemId, string eventType, string matchData, class Microsoft.ReportingServices.Library.Soap.ExtensionSettings extensionSettings, string description, class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, unsigned int8[] securityDescriptor)
0x28807  stloc.s  4
0x28809  ldloc.0
0x2880a  brtrue.s loc_28820
0x2880c  ldarg.0
0x2880d  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x28812  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.EventManager Microsoft.ReportingServices.Library.RSService::get_EventManager()
0x28817  ldarg.s  5
0x28819  ldloc.s  4
0x2881b  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.EventManager::FireEvent(string, string)
0x28820  leave.s  loc_2882E
0x28822  ldarg.0
0x28823  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DeliverReportItemAction::m_service
0x28828  callvirt instance void Microsoft.ReportingServices.Library.RSService::DisconnectStorage()
0x2882d  endfinally
0x2882e  ret
```
