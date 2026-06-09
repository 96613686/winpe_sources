# Microsoft.ReportingServices.Library.StreamRequestHandler::ExecuteCommand

- ea: `0x6b060`
- end: `0x6b55d`
- name: `Microsoft.ReportingServices.Library.StreamRequestHandler::ExecuteCommand`
- size: `1277`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x19a50`
- `0x19a60`
- `0x6aeb0`
- `0x6aed0`
- `0x6af40`
- `0x6af60`
- `0x6af90`
- `0x6b030`
- `0x6b060`
- `0x6b560`
- `0x6b7c0`
- `0x6b810`
- `0x6b8c0`
- `0x6bfd0`
- `0x6cef0`
- `0x6cfa0`
- `0x6cff0`
- `0x6d070`
- `0x6d0b0`
- `0x6d200`
- `0x87790`

## string_xrefs

- `0x6b394`: `GetComponentDefinition`
- `0x6b066`: `pv:Command`
- `0x6b07a`: `rs:Command`
- `0x6b08b`: `Entering StreamRequestHandler.ExecuteCommand - Command = {0}`
- `0x6b09f`: `StreamRequestHandler.ExecuteCommand - Command = `
- `0x6b548`: `Exiting StreamRequestHandler.ExecuteCommand - Command = {0} (success)`

## pseudocode

```c

```

## disassembly

```asm
0x6b060  ldarg.0
0x6b061  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6b066  ldstr    aPvCommand// "pv:Command"
0x6b06b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6b070  stloc.0
0x6b071  ldloc.0
0x6b072  brtrue.s loc_6B085
0x6b074  ldarg.0
0x6b075  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6b07a  ldstr    aRsCommand// "rs:Command"
0x6b07f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6b084  stloc.0
0x6b085  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6b08a  ldc.i4.3
0x6b08b  ldstr    aEnteringStream// "Entering StreamRequestHandler.ExecuteCo"...
0x6b090  ldc.i4.1
0x6b091  newarr   [mscorlib]System.Object
0x6b096  dup
0x6b097  ldc.i4.0
0x6b098  ldloc.0
0x6b099  stelem.ref
0x6b09a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6b09f  ldstr    aStreamrequesth// "StreamRequestHandler.ExecuteCommand - C"...
0x6b0a4  ldloc.0
0x6b0a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::NewConcat(string, object)
0x6b0aa  stloc.1
0x6b0ab  ldc.i4.s 0xF
0x6b0ad  stloc.2
0x6b0ae  ldarg.0
0x6b0af  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x6b0b4  ldarg.0
0x6b0b5  call     instance string Microsoft.ReportingServices.Library.StreamRequestHandler::get_NormalizedItemPath()
0x6b0ba  ldloc.2
0x6b0bb  callvirt instance bool class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::SetPath(string, valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathOptions)
0x6b0c0  brtrue.s loc_6B0CE
0x6b0c2  ldarg.0
0x6b0c3  call     instance string Microsoft.ReportingServices.Library.StreamRequestHandler::get_NormalizedItemPath()
0x6b0c8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemPathException::.ctor(string)
0x6b0cd  throw
0x6b0ce  ldarg.0
0x6b0cf  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x6b0d4  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_OriginalItemPath()
0x6b0d9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6b0de  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::GetParentPathForSharePoint(string)
0x6b0e3  stloc.3
0x6b0e4  ldarg.0
0x6b0e5  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6b0ea  ldloc.3
0x6b0eb  callvirt instance void Microsoft.ReportingServices.Library.RSService::EnsureSecurityZone(string itemPath)
0x6b0f0  ldarg.0
0x6b0f1  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6b0f6  ldloc.3
0x6b0f7  callvirt instance void Microsoft.ReportingServices.Library.RSService::PopulateAdditionalToken(string itemPath)
0x6b0fc  ldarg.0
0x6b0fd  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x6b102  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x6b107  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x6b10c  brfalse.s loc_6B114
0x6b10e  ldstr    aRender// "Render"
0x6b113  stloc.0
0x6b114  ldloc.0
0x6b115  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x6b11a  stloc.s  4
0x6b11c  ldloc.s  4
0x6b11e  ldc.i4   0x96028716
0x6b123  bgt.un   loc_6B1DB
0x6b128  ldloc.s  4
0x6b12a  ldc.i4   0x40CD62EF
0x6b12f  bgt.un.s loc_6B180
0x6b131  ldloc.s  4
0x6b133  ldc.i4   0x121AB409
0x6b138  bgt.un.s loc_6B157
0x6b13a  ldloc.s  4
0x6b13c  ldc.i4   0x4AC0F48
0x6b141  beq      loc_6B3E7
0x6b146  ldloc.s  4
0x6b148  ldc.i4   0x121AB409
0x6b14d  beq      loc_6B3A8
0x6b152  br       loc_6B530
0x6b157  ldloc.s  4
0x6b159  ldc.i4   0x1B4E264E
0x6b15e  beq      loc_6B3FC
0x6b163  ldloc.s  4
0x6b165  ldc.i4   0x350CF42D
0x6b16a  beq      loc_6B297
0x6b16f  ldloc.s  4
0x6b171  ldc.i4   0x40CD62EF
0x6b176  beq      loc_6B315
0x6b17b  br       loc_6B530
0x6b180  ldloc.s  4
0x6b182  ldc.i4   0x6546E1E1
0x6b187  bgt.un.s loc_6B1B2
0x6b189  ldloc.s  4
0x6b18b  ldc.i4   0x42E40961
0x6b190  beq      loc_6B32A
0x6b195  ldloc.s  4
0x6b197  ldc.i4   0x64678ABD
0x6b19c  beq      loc_6B300
0x6b1a1  ldloc.s  4
0x6b1a3  ldc.i4   0x6546E1E1
0x6b1a8  beq      loc_6B369
0x6b1ad  br       loc_6B530
0x6b1b2  ldloc.s  4
0x6b1b4  ldc.i4   0x8459A7F1
0x6b1b9  beq      loc_6B33F
0x6b1be  ldloc.s  4
0x6b1c0  ldc.i4   0x8A4169C2
0x6b1c5  beq      loc_6B411
0x6b1ca  ldloc.s  4
0x6b1cc  ldc.i4   0x96028716
0x6b1d1  beq      loc_6B37E
0x6b1d6  br       loc_6B530
0x6b1db  ldloc.s  4
0x6b1dd  ldc.i4   0xB6973EF7
0x6b1e2  bgt.un.s loc_6B230
0x6b1e4  ldloc.s  4
0x6b1e6  ldc.i4   0xAC48B84E
0x6b1eb  bgt.un.s loc_6B20A
0x6b1ed  ldloc.s  4
0x6b1ef  ldc.i4   0xA121335C
0x6b1f4  beq      loc_6B354
0x6b1f9  ldloc.s  4
0x6b1fb  ldc.i4   0xAC48B84E
0x6b200  beq      loc_6B43B
0x6b205  br       loc_6B530
0x6b20a  ldloc.s  4
0x6b20c  ldc.i4   0xAD0D5A54
0x6b211  beq      loc_6B3D2
0x6b216  ldloc.s  4
0x6b218  ldc.i4   0xB33D7AE0
0x6b21d  beq      loc_6B2EB
0x6b222  ldloc.s  4
0x6b224  ldc.i4   0xB6973EF7
0x6b229  beq.s    loc_6B282
0x6b22b  br       loc_6B530
0x6b230  ldloc.s  4
0x6b232  ldc.i4   0xCD7D540E
0x6b237  bgt.un.s loc_6B25C
0x6b239  ldloc.s  4
0x6b23b  ldc.i4   0xB6BF5F75
0x6b240  beq.s    loc_6B2C1
0x6b242  ldloc.s  4
0x6b244  ldc.i4   0xCA833D94
0x6b249  beq      loc_6B3BD
0x6b24e  ldloc.s  4
0x6b250  ldc.i4   0xCD7D540E
0x6b255  beq.s    loc_6B2AC
0x6b257  br       loc_6B530
0x6b25c  ldloc.s  4
0x6b25e  ldc.i4   0xD3DB7CCD
0x6b263  beq      loc_6B426
0x6b268  ldloc.s  4
0x6b26a  ldc.i4   0xDB8989E0
0x6b26f  beq.s    loc_6B2D6
0x6b271  ldloc.s  4
0x6b273  ldc.i4   0xF8745003
0x6b278  beq      loc_6B393
0x6b27d  br       loc_6B530
0x6b282  ldloc.0
0x6b283  ldstr    aGet// "Get"
0x6b288  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b28d  brtrue   loc_6B450
0x6b292  br       loc_6B530
0x6b297  ldloc.0
0x6b298  ldstr    aRender// "Render"
0x6b29d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b2a2  brtrue   loc_6B467
0x6b2a7  br       loc_6B530
0x6b2ac  ldloc.0
0x6b2ad  ldstr    aListchildren// "ListChildren"
0x6b2b2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b2b7  brtrue   loc_6B473
0x6b2bc  br       loc_6B530
0x6b2c1  ldloc.0
0x6b2c2  ldstr    aGetresourcecon_0// "GetResourceContents"
0x6b2c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b2cc  brtrue   loc_6B485
0x6b2d1  br       loc_6B530
0x6b2d6  ldloc.0
0x6b2d7  ldstr    aGetdatasourcec_0// "GetDataSourceContents"
0x6b2dc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b2e1  brtrue   loc_6B497
0x6b2e6  br       loc_6B530
0x6b2eb  ldloc.0
0x6b2ec  ldstr    aGetdatasetdefi_0// "GetDataSetDefinition"
0x6b2f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b2f6  brtrue   loc_6B4A9
0x6b2fb  br       loc_6B530
0x6b300  ldloc.0
0x6b301  ldstr    aGetmodeldefini_0// "GetModelDefinition"
0x6b306  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b30b  brtrue   loc_6B4BB
0x6b310  br       loc_6B530
0x6b315  ldloc.0
0x6b316  ldstr    aDrillthrough// "Drillthrough"
0x6b31b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b320  brtrue   loc_6B4BB
0x6b325  br       loc_6B530
0x6b32a  ldloc.0
0x6b32b  ldstr    aBlank// "Blank"
0x6b330  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b335  brtrue   loc_6B4CA
0x6b33a  br       loc_6B530
0x6b33f  ldloc.0
0x6b340  ldstr    aSort// "Sort"
0x6b345  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b34a  brtrue   loc_6B4D8
0x6b34f  br       loc_6B530
0x6b354  ldloc.0
0x6b355  ldstr    aExecutequery// "ExecuteQuery"
0x6b35a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b35f  brtrue   loc_6B4EC
0x6b364  br       loc_6B530
0x6b369  ldloc.0
0x6b36a  ldstr    aStylesheet// "StyleSheet"
0x6b36f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b374  brtrue   loc_6B4FB
0x6b379  br       loc_6B530
0x6b37e  ldloc.0
0x6b37f  ldstr    aStylesheetimag// "StyleSheetImage"
0x6b384  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b389  brtrue   loc_6B509
0x6b38e  br       loc_6B530
0x6b393  ldloc.0
0x6b394  ldstr    aGetcomponentde// "GetComponentDefinition"
0x6b399  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b39e  brtrue   loc_6B511
0x6b3a3  br       loc_6B530
0x6b3a8  ldloc.0
0x6b3a9  ldstr    aRenderedit// "RenderEdit"
0x6b3ae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b3b3  brtrue   loc_6B521
0x6b3b8  br       loc_6B530
0x6b3bd  ldloc.0
0x6b3be  ldstr    aGetmodel// "GetModel"
0x6b3c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b3c8  brtrue   loc_6B521
0x6b3cd  br       loc_6B530
0x6b3d2  ldloc.0
0x6b3d3  ldstr    aGetreportandmo_0// "GetReportAndModels"
0x6b3d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b3dd  brtrue   loc_6B521
0x6b3e2  br       loc_6B530
0x6b3e7  ldloc.0
0x6b3e8  ldstr    aExecutequeries_1// "ExecuteQueries"
0x6b3ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b3f2  brtrue   loc_6B521
0x6b3f7  br       loc_6B530
0x6b3fc  ldloc.0
0x6b3fd  ldstr    aGetexternalima_3// "GetExternalImages"
0x6b402  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b407  brtrue   loc_6B521
0x6b40c  br       loc_6B530
0x6b411  ldloc.0
0x6b412  ldstr    aLogclienttrace_3// "LogClientTraceEvents"
0x6b417  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b41c  brtrue   loc_6B521
0x6b421  br       loc_6B530
0x6b426  ldloc.0
0x6b427  ldstr    aClosesession// "CloseSession"
0x6b42c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b431  brtrue   loc_6B521
0x6b436  br       loc_6B530
0x6b43b  ldloc.0
0x6b43c  ldstr    aCancelprogress_0// "CancelProgressiveSessionJobs"
0x6b441  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b446  brtrue   loc_6B521
0x6b44b  br       loc_6B530
0x6b450  ldarg.0
0x6b451  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::DisallowEditSession()
0x6b456  ldarg.0
0x6b457  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::PopulateRSRequestParameters()
0x6b45c  ldarg.0
0x6b45d  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::HandleGetRequest()
0x6b462  leave    loc_6B542
0x6b467  ldarg.0
0x6b468  ldc.i4.2
0x6b469  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::RenderItem(valuetype Microsoft.ReportingServices.Library.ItemType itemType)
0x6b46e  leave    loc_6B542
0x6b473  ldarg.0
0x6b474  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::DisallowEditSession()
0x6b479  ldarg.0
0x6b47a  ldc.i4.1
0x6b47b  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::RenderItem(valuetype Microsoft.ReportingServices.Library.ItemType itemType)
0x6b480  leave    loc_6B542
0x6b485  ldarg.0
0x6b486  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::DisallowEditSession()
0x6b48b  ldarg.0
0x6b48c  ldc.i4.3
0x6b48d  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::RenderItem(valuetype Microsoft.ReportingServices.Library.ItemType itemType)
0x6b492  leave    loc_6B542
0x6b497  ldarg.0
0x6b498  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::DisallowEditSession()
0x6b49d  ldarg.0
0x6b49e  ldc.i4.5
0x6b49f  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::RenderItem(valuetype Microsoft.ReportingServices.Library.ItemType itemType)
0x6b4a4  leave    loc_6B542
0x6b4a9  ldarg.0
0x6b4aa  call     instance void Microsoft.ReportingServices.Library.StreamRequestHandler::DisallowEditSession()
0x6b4af  ldarg.0
  ... truncated ...
```
