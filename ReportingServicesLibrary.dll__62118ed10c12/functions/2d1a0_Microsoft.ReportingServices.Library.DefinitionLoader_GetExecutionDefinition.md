# Microsoft.ReportingServices.Library.DefinitionLoader::GetExecutionDefinition

- ea: `0x2d1a0`
- end: `0x2d453`
- name: `Microsoft.ReportingServices.Library.DefinitionLoader::GetExecutionDefinition`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e220`

## callees

- `0x4610`
- `0x5b30`
- `0x7930`
- `0xee80`
- `0x1d6c0`
- `0x1d880`
- `0x1e270`
- `0x1e570`
- `0x221d0`
- `0x225d0`
- `0x23420`
- `0x2c710`
- `0x2c930`
- `0x2d1a0`
- `0x2d6c0`
- `0x2dc10`
- `0x2dc20`
- `0x2e250`
- `0x2e380`
- `0x2e3a0`
- `0x2e3c0`
- `0x2e620`
- `0x5bb20`
- `0x5e070`
- `0x5e0b0`
- `0x5ea50`
- `0x5eb30`
- `0x5eb50`
- `0x5eb90`
- `0x5ebd0`
- `0x5ed90`

## string_xrefs

- `0x2d3e1`: `DefinitionLoader.GetExecutionDefinition(): !foundInCache`

## pseudocode

```c

```

## disassembly

```asm
0x2d1a0  ldarg.0
0x2d1a1  ldarg.1
0x2d1a2  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::m_itemContext
0x2d1a7  ldarg.0
0x2d1a8  ldarg.s  4
0x2d1aa  stfld    class Microsoft.ReportingServices.Library.SecurityRequirements Microsoft.ReportingServices.Library.DefinitionLoader::m_requirements
0x2d1af  ldarg.2
0x2d1b0  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d1b5  callvirt instance bool Microsoft.ReportingServices.Library.SessionReportItem::get_IsAdhocReport()
0x2d1ba  brfalse  loc_2D25A
0x2d1bf  ldarg.1
0x2d1c0  ldarg.2
0x2d1c1  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d1c6  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x2d1cb  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_CompiledDefinition()
0x2d1d0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d1d5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d1da  ldarg.2
0x2d1db  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d1e0  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x2d1e5  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x2d1ea  ldc.i4.2
0x2d1eb  ldarg.1
0x2d1ec  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_ReportDefinitionAsExternalItemPath()
0x2d1f1  ldnull
0x2d1f2  ldnull
0x2d1f3  ldnull
0x2d1f4  call     int32 Microsoft.ReportingServices.Library.ExecutionOptions::get_Live()
0x2d1f9  ldarg.2
0x2d1fa  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d1ff  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x2d204  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x2d209  ldnull
0x2d20a  cgt.un
0x2d20c  ldc.i4.0
0x2d20d  ldc.i4.0
0x2d20e  ldc.i4.0
0x2d20f  ldarg.2
0x2d210  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d215  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SessionReportItem::get_ExecutionDateTime()
0x2d21a  ldarg.2
0x2d21b  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d220  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SessionReportItem::get_ExpirationDateTime()
0x2d225  newobj   instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, class Microsoft.ReportingServices.Library.ReportSnapshot definitionSnapshot, valuetype [mscorlib]System.Guid reportId, valuetype [mscorlib]System.Guid linkId, class Microsoft.ReportingServices.Library.ReportSnapshot snapshotData, valuetype Microsoft.ReportingServices.Library.ItemType itemType, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath reportDefinitionPath, string properties, string description, unsigned int8[] securityDescriptor, int32 executionOptions, bool hasData, bool foundInCache, bool cachingRequested, bool isRdceReport, valuetype [mscorlib]System.DateTime executionDateTime, valuetype [mscorlib]System.DateTime expirationDateTime)
0x2d22a  dup
0x2d22b  ldarg.2
0x2d22c  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d231  callvirt instance int32 Microsoft.ReportingServices.Library.SessionReportItem::get_PageCount()
0x2d236  ldarg.2
0x2d237  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2d23c  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PaginationMode Microsoft.ReportingServices.Library.SessionReportItem::get_PaginationMode()
0x2d241  newobj   instance void Microsoft.ReportingServices.Library.ReportPaginationData::.ctor(int32 pageCount, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PaginationMode mode)
0x2d246  callvirt instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::set_PaginationData(class Microsoft.ReportingServices.Library.ReportPaginationData value)
0x2d24b  dup
0x2d24c  ldnull
0x2d24d  callvirt instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::set_DataSources(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection value)
0x2d252  dup
0x2d253  ldnull
0x2d254  callvirt instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::set_DataSets(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection value)
0x2d259  ret
0x2d25a  ldarg.0
0x2d25b  call     instance bool Microsoft.ReportingServices.Library.DefinitionLoader::CheckSecurityAndRepublish()
0x2d260  ldarg.0
0x2d261  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DefinitionLoader::m_service
0x2d266  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x2d26b  newobj   instance void Microsoft.ReportingServices.Library.DBInterface::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext userContext)
0x2d270  stloc.0
0x2d271  ldloc.0
0x2d272  ldarg.0
0x2d273  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.DefinitionLoader::m_connection
0x2d278  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x2d27d  ldarg.3
0x2d27e  ldc.i4.1
0x2d27f  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::ToXml(bool)
0x2d284  stloc.s  0x10
0x2d286  ldloc.0
0x2d287  ldarg.0
0x2d288  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2d28d  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x2d292  ldloc.s  0x10
0x2d294  ldloca.s 1
0x2d296  ldloca.s 0xE
0x2d298  ldloca.s 4
0x2d29a  ldloca.s 5
0x2d29c  ldloca.s 6
0x2d29e  ldloca.s 8
0x2d2a0  ldloca.s 9
0x2d2a2  ldloca.s 0xA
0x2d2a4  ldloca.s 0xD
0x2d2a6  ldloca.s 7
0x2d2a8  ldloca.s 0xF
0x2d2aa  ldloca.s 0xB
0x2d2ac  ldloca.s 2
0x2d2ae  ldloca.s 3
0x2d2b0  ldloca.s 0xC
0x2d2b2  callvirt instance bool Microsoft.ReportingServices.Library.DBInterface::GetReportForExecution(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath objectName, string queryParametersXml, [out] bool& foundInCache, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type, [out] class Microsoft.ReportingServices.Library.ReportSnapshot& intermediateSnapshot, [out] class Microsoft.ReportingServices.Library.ReportSnapshot& snapshotData, [out] valuetype [mscorlib]System.Guid& link, [out] string& linkPath, [out] string& properties, [out] string& description, [out] unsigned int8[]& secDesc, [out] valuetype [mscorlib]System.Guid& reportID, [out] int32& execOptions, [out] valuetype [mscorlib]System.DateTime& executionDateTime, [out] bool& hasData, [out] bool& cachingRequested, [out] valuetype [mscorlib]System.DateTime& expirationDateTime)
0x2d2b7  brtrue.s loc_2D2CA
0x2d2b9  ldarg.0
0x2d2ba  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_OriginalItemPath()
0x2d2bf  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x2d2c4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x2d2c9  throw
0x2d2ca  ldloc.s  0xE
0x2d2cc  ldarg.0
0x2d2cd  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_OriginalItemPath()
0x2d2d2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x2d2d7  call     void Microsoft.ReportingServices.Library.RSService::EnsureItemTypeIsReport(valuetype Microsoft.ReportingServices.Library.ItemType actualType, string path)
0x2d2dc  brtrue.s loc_2D2EF
0x2d2de  ldarg.s  4
0x2d2e0  ldloc.s  0xE
0x2d2e2  ldloc.s  0xD
0x2d2e4  ldarg.0
0x2d2e5  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_OriginalItemPath()
0x2d2ea  callvirt instance void Microsoft.ReportingServices.Library.SecurityRequirements::CheckAccess(valuetype Microsoft.ReportingServices.Library.ItemType itemType, unsigned int8[] securityDescriptor, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x2d2ef  ldloc.s  0xE
0x2d2f1  ldc.i4.4
0x2d2f2  bne.un.s loc_2D31B
0x2d2f4  ldloc.s  6
0x2d2f6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d2fb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2d300  brfalse.s loc_2D308
0x2d302  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidReportLinkException::.ctor()
0x2d307  throw
0x2d308  ldarg.1
0x2d309  ldarg.0
0x2d30a  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DefinitionLoader::m_service
0x2d30f  ldloc.s  8
0x2d311  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.RSService::CatalogToExternal(string source)
0x2d316  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetReportDefinitionPath(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath)
0x2d31b  ldloc.1
0x2d31c  brtrue.s loc_2D32B
0x2d31e  ldloc.2
0x2d31f  brfalse.s loc_2D32B
0x2d321  ldloc.s  5
0x2d323  brtrue.s loc_2D32B
0x2d325  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportNotReadyException::.ctor()
0x2d32a  throw
0x2d32b  ldc.i4.0
0x2d32c  stloc.s  0x11
0x2d32e  ldc.i4.1
0x2d32f  stloc.s  0x12
0x2d331  ldc.i4.0
0x2d332  stloc.s  0x13
0x2d334  ldarg.1
0x2d335  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x2d33a  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x2d33f  ldc.i4.0
0x2d340  ceq
0x2d342  ldloc.2
0x2d343  and
0x2d344  brfalse.s loc_2D368
0x2d346  ldarg.1
0x2d347  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x2d34c  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_SnapshotParamValue()
0x2d351  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d356  brfalse.s loc_2D368
0x2d358  ldloc.0
0x2d359  ldloc.s  5
0x2d35b  ldloca.s 0x13
0x2d35d  ldloca.s 0x12
0x2d35f  ldloca.s 0x17
0x2d361  callvirt instance int32 Microsoft.ReportingServices.Library.DBInterface::GetSnapshotPromotedInfo(class Microsoft.ReportingServices.Library.ReportSnapshot reportSnapshot, [out] bool& hasDocMap, [out] valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PaginationMode& paginationMode, [out] valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags& processingFlags)
0x2d366  stloc.s  0x11
0x2d368  ldloc.s  0x11
0x2d36a  ldloc.s  0x12
0x2d36c  newobj   instance void Microsoft.ReportingServices.Library.ReportPaginationData::.ctor(int32 pageCount, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PaginationMode mode)
0x2d371  stloc.s  0x14
0x2d373  ldarg.0
0x2d374  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DefinitionLoader::m_service
0x2d379  callvirt instance class Microsoft.ReportingServices.Library.CatalogItemFactory Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0x2d37e  ldarg.1
0x2d37f  ldloc.s  7
0x2d381  ldloc.s  0xE
0x2d383  ldloc.s  0xD
0x2d385  ldloc.s  6
0x2d387  callvirt instance class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, valuetype [mscorlib]System.Guid itemID, valuetype Microsoft.ReportingServices.Library.ItemType itemType, unsigned int8[] secDesc, valuetype [mscorlib]System.Guid linkId)
0x2d38c  isinst   Microsoft.ReportingServices.Library.BaseReportCatalogItem
0x2d391  stloc.s  0x15
0x2d393  ldarg.0
0x2d394  ldloc.s  0x15
0x2d396  ldarg.0
0x2d397  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DefinitionLoader::m_service
0x2d39c  ldloc.s  8
0x2d39e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.RSService::CatalogToExternal(string source)
0x2d3a3  ldloc.s  9
0x2d3a5  ldarg.3
0x2d3a6  call     instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.DefinitionLoader::CheckRdceAndGenerateSnapshot(class Microsoft.ReportingServices.Library.BaseReportCatalogItem reportItem, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath linkPath, string properties, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection queryParameters)
0x2d3ab  stloc.s  0x16
0x2d3ad  ldloc.s  0x16
0x2d3af  brfalse.s loc_2D3FE
0x2d3b1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d3b6  ldloc.s  5
0x2d3b8  ldnull
0x2d3b9  ceq
0x2d3bb  ldstr    aDefinitionload_2// "DefinitionLoader.GetExecutionDefinition"...
0x2d3c0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d3c5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d3ca  ldloc.2
0x2d3cb  ldc.i4.0
0x2d3cc  ceq
0x2d3ce  ldstr    aDefinitionload_3// "DefinitionLoader.GetExecutionDefinition"...
0x2d3d3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d3d8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d3dd  ldloc.1
0x2d3de  ldc.i4.0
0x2d3df  ceq
0x2d3e1  ldstr    aDefinitionload_4// "DefinitionLoader.GetExecutionDefinition"...
0x2d3e6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d3eb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d3f0  ldloc.3
0x2d3f1  ldc.i4.0
0x2d3f2  ceq
0x2d3f4  ldstr    aDefinitionload_5// "DefinitionLoader.GetExecutionDefinition"...
0x2d3f9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d3fe  ldarg.1
0x2d3ff  ldloc.s  0x16
0x2d401  brfalse.s loc_2D407
0x2d403  ldloc.s  0x16
0x2d405  br.s     loc_2D409
0x2d407  ldloc.s  4
0x2d409  ldloc.s  7
0x2d40b  ldloc.s  6
0x2d40d  ldloc.s  5
0x2d40f  ldloc.s  0xE
0x2d411  ldarg.1
0x2d412  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_ReportDefinitionAsExternalItemPath()
0x2d417  ldloc.s  9
0x2d419  ldloc.s  0xA
0x2d41b  ldloc.s  0xD
0x2d41d  ldloc.s  0xF
0x2d41f  ldloc.2
0x2d420  ldloc.1
0x2d421  ldloc.3
0x2d422  ldloc.s  0x16
0x2d424  ldnull
0x2d425  cgt.un
0x2d427  ldloc.s  0xB
0x2d429  ldloc.s  0xC
0x2d42b  newobj   instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, class Microsoft.ReportingServices.Library.ReportSnapshot definitionSnapshot, valuetype [mscorlib]System.Guid reportId, valuetype [mscorlib]System.Guid linkId, class Microsoft.ReportingServices.Library.ReportSnapshot snapshotData, valuetype Microsoft.ReportingServices.Library.ItemType itemType, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath reportDefinitionPath, string properties, string description, unsigned int8[] securityDescriptor, int32 executionOptions, bool hasData, bool foundInCache, bool cachingRequested, bool isRdceReport, valuetype [mscorlib]System.DateTime executionDateTime, valuetype [mscorlib]System.DateTime expirationDateTime)
0x2d430  dup
0x2d431  ldloc.s  0x14
0x2d433  callvirt instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::set_PaginationData(class Microsoft.ReportingServices.Library.ReportPaginationData value)
0x2d438  dup
0x2d439  ldloc.s  0x15
0x2d43b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection Microsoft.ReportingServices.Library.BaseExecutableCatalogItem::get_DataSources()
0x2d440  callvirt instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::set_DataSources(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection value)
0x2d445  dup
0x2d446  ldloc.s  0x15
0x2d448  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection Microsoft.ReportingServices.Library.BaseReportCatalogItem::get_SharedDataSets()
0x2d44d  callvirt instance void Microsoft.ReportingServices.Library.ReportExecutionDefinition::set_DataSets(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection value)
0x2d452  ret
```
