# Microsoft.ReportingServices.Library.DefinitionLoader::CheckSecurityAndRepublish

- ea: `0x2d6c0`
- end: `0x2d856`
- name: `Microsoft.ReportingServices.Library.DefinitionLoader::CheckSecurityAndRepublish`
- size: `406`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d050`
- `0x2d1a0`
- `0x2d590`

## callees

- `0x2d6a0`
- `0x2d6c0`
- `0x2d860`
- `0x2dbd0`
- `0x2dc00`
- `0x2dc10`
- `0x2dc20`
- `0x2dd80`
- `0x2e010`
- `0x2e620`
- `0x2e710`
- `0x2e770`
- `0x5ff80`
- `0x637b0`

## string_xrefs

- `0x2d6de`: `ItemPath`
- `0x2d6f6`: `OriginalItemPath`
- `0x2d7af`: `compiledDefinition`
- `0x2d7ce`: `compiledDefinition.SnapshotDataId`

## pseudocode

```c

```

## disassembly

```asm
0x2d6c0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d6c5  ldarg.0
0x2d6c6  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemPath()
0x2d6cb  brfalse.s loc_2D6DD
0x2d6cd  ldarg.0
0x2d6ce  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemPath()
0x2d6d3  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x2d6d8  ldnull
0x2d6d9  cgt.un
0x2d6db  br.s     loc_2D6DE
0x2d6dd  ldc.i4.0
0x2d6de  ldstr    aItempath// "ItemPath"
0x2d6e3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d6e8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d6ed  ldarg.0
0x2d6ee  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_OriginalItemPath()
0x2d6f3  ldnull
0x2d6f4  cgt.un
0x2d6f6  ldstr    aOriginalitempa// "OriginalItemPath"
0x2d6fb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d700  ldarg.0
0x2d701  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemPath()
0x2d706  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x2d70b  brfalse.s loc_2D70F
0x2d70d  ldc.i4.0
0x2d70e  ret
0x2d70f  ldarg.0
0x2d710  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2d715  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x2d71a  call     bool Microsoft.ReportingServices.Library.RepublishingCache::HasPathBeenChecked(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath itemPath)
0x2d71f  brfalse.s loc_2D72A
0x2d721  ldsfld   bool Microsoft.ReportingServices.Library.DefinitionLoader::m_forceRepublishing
0x2d726  brtrue.s loc_2D72A
0x2d728  ldc.i4.0
0x2d729  ret
0x2d72a  ldarg.0
0x2d72b  ldloca.s 0
0x2d72d  call     instance bool Microsoft.ReportingServices.Library.DefinitionLoader::GetRepublishCheckConnection([out] class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager& connection)
0x2d732  stloc.1
0x2d733  ldloc.1
0x2d734  brfalse.s loc_2D760
0x2d736  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d73b  ldloc.0
0x2d73c  ldarg.0
0x2d73d  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.DefinitionLoader::m_connection
0x2d742  ceq
0x2d744  ldc.i4.0
0x2d745  ceq
0x2d747  ldstr    aConnectionMCon// "connection != m_connection"
0x2d74c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d751  ldloc.0
0x2d752  ldc.i4.0
0x2d753  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::set_ConnectionTransactionType(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType)
0x2d758  ldloc.0
0x2d759  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x2d75e  br.s     loc_2D778
0x2d760  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d765  ldloc.0
0x2d766  ldarg.0
0x2d767  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.DefinitionLoader::m_connection
0x2d76c  ceq
0x2d76e  ldstr    aConnectionMCon_0// "connection == m_connection"
0x2d773  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d778  nop
0x2d779  newobj   instance void Microsoft.ReportingServices.Library.DefinitionDbInterface::.ctor()
0x2d77e  stloc.2
0x2d77f  ldloc.2
0x2d780  ldloc.0
0x2d781  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x2d786  ldloc.2
0x2d787  ldarg.0
0x2d788  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2d78d  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x2d792  ldc.i4.0
0x2d793  ldloca.s 3
0x2d795  ldloca.s 4
0x2d797  callvirt instance bool Microsoft.ReportingServices.Library.DefinitionDbInterface::LoadForDefinitionCheck(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath itemPath, bool acquireUpdateLocks, [out] class Microsoft.ReportingServices.Library.ReportSnapshot& compiledDefinition, [out] unsigned int8[]& secDesc)
0x2d79c  brtrue.s loc_2D7A6
0x2d79e  ldc.i4.0
0x2d79f  stloc.s  5
0x2d7a1  leave    loc_2D853
0x2d7a6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d7ab  ldloc.3
0x2d7ac  ldnull
0x2d7ad  cgt.un
0x2d7af  ldstr    aCompileddefini// "compiledDefinition"
0x2d7b4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d7b9  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d7be  ldloc.3
0x2d7bf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x2d7c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d7c9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2d7ce  ldstr    aCompileddefini_0// "compiledDefinition.SnapshotDataId"
0x2d7d3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d7d8  ldarg.0
0x2d7d9  ldfld    class Microsoft.ReportingServices.Library.SecurityRequirements Microsoft.ReportingServices.Library.DefinitionLoader::m_requirements
0x2d7de  ldc.i4.2
0x2d7df  ldloc.s  4
0x2d7e1  ldarg.0
0x2d7e2  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemPath()
0x2d7e7  callvirt instance void Microsoft.ReportingServices.Library.SecurityRequirements::CheckAccess(valuetype Microsoft.ReportingServices.Library.ItemType itemType, unsigned int8[] securityDescriptor, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x2d7ec  ldarg.0
0x2d7ed  call     instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessing/NeedsUpgrade Microsoft.ReportingServices.Library.DefinitionLoader::get_UpgradeCheckCallback()
0x2d7f2  ldloc.3
0x2d7f3  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags Microsoft.ReportingServices.Library.ReportSnapshot::get_ProcessingFlags()
0x2d7f8  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessing/NeedsUpgrade::Invoke(valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags)
0x2d7fd  brtrue.s loc_2D823
0x2d7ff  ldsfld   bool Microsoft.ReportingServices.Library.DefinitionLoader::m_forceRepublishing
0x2d804  brtrue.s loc_2D823
0x2d806  ldloc.3
0x2d807  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags Microsoft.ReportingServices.Library.ReportSnapshot::get_ProcessingFlags()
0x2d80c  brfalse.s loc_2D81E
0x2d80e  ldarg.0
0x2d80f  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2d814  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x2d819  call     void Microsoft.ReportingServices.Library.RepublishingCache::MarkPathAsChecked(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath itemPath)
0x2d81e  ldc.i4.1
0x2d81f  stloc.s  5
0x2d821  leave.s  loc_2D853
0x2d823  ldarg.0
0x2d824  ldloc.2
0x2d825  ldloc.3
0x2d826  call     instance void Microsoft.ReportingServices.Library.DefinitionLoader::Republish(class Microsoft.ReportingServices.Library.DefinitionDbInterface storage, class Microsoft.ReportingServices.Library.ReportSnapshot originalCompiledDefinition)
0x2d82b  ldloc.1
0x2d82c  brfalse.s loc_2D844
0x2d82e  ldloc.0
0x2d82f  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x2d834  ldarg.0
0x2d835  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2d83a  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x2d83f  call     void Microsoft.ReportingServices.Library.RepublishingCache::MarkPathAsChecked(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath itemPath)
0x2d844  ldc.i4.1
0x2d845  stloc.s  5
0x2d847  leave.s  loc_2D853
0x2d849  ldloc.1
0x2d84a  brfalse.s loc_2D852
0x2d84c  ldloc.0
0x2d84d  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x2d852  endfinally
0x2d853  ldloc.s  5
0x2d855  ret
```
