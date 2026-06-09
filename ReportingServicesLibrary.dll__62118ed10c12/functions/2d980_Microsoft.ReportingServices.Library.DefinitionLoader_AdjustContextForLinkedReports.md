# Microsoft.ReportingServices.Library.DefinitionLoader::AdjustContextForLinkedReports

- ea: `0x2d980`
- end: `0x2da4e`
- name: `Microsoft.ReportingServices.Library.DefinitionLoader::AdjustContextForLinkedReports`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d860`

## callees

- `0x4610`
- `0x53d0`
- `0x6b30`
- `0x1e570`
- `0x2d980`
- `0x2dc00`
- `0x2dc20`

## string_xrefs

- `0x2d9be`: `!ItemPath.IsEditSession`
- `0x2da38`: `RepublishingPath`

## pseudocode

```c

```

## disassembly

```asm
0x2d980  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d985  ldarg.1
0x2d986  ldnull
0x2d987  cgt.un
0x2d989  ldstr    aConnectionmana// "connectionManager"
0x2d98e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d993  ldarg.0
0x2d994  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DefinitionLoader::m_service
0x2d999  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x2d99e  newobj   instance void Microsoft.ReportingServices.Library.DBInterface::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext userContext)
0x2d9a3  stloc.1
0x2d9a4  ldloc.1
0x2d9a5  ldarg.1
0x2d9a6  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x2d9ab  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2d9b0  ldarg.0
0x2d9b1  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemPath()
0x2d9b6  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x2d9bb  ldc.i4.0
0x2d9bc  ceq
0x2d9be  ldstr    aItempathIsedit// "!ItemPath.IsEditSession"
0x2d9c3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2d9c8  ldloc.1
0x2d9c9  ldarg.0
0x2d9ca  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2d9cf  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x2d9d4  ldloca.s 2
0x2d9d6  ldloca.s 3
0x2d9d8  ldloca.s 6
0x2d9da  ldloca.s 8
0x2d9dc  ldloca.s 7
0x2d9de  ldloca.s 5
0x2d9e0  ldloca.s 4
0x2d9e2  callvirt instance bool Microsoft.ReportingServices.Library.DBInterface::CatalogObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type, [out] valuetype [mscorlib]System.Guid& id, [out] int32& snapshotLimit, [out] unsigned int8[]& secDesc, [out] int32& execOptions, [out] valuetype [mscorlib]System.Guid& snapshotId, [out] valuetype [mscorlib]System.Guid& linkID)
0x2d9e7  brtrue.s loc_2D9FF
0x2d9e9  ldarg.0
0x2d9ea  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2d9ef  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_OriginalItemPath()
0x2d9f4  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x2d9f9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x2d9fe  throw
0x2d9ff  ldloc.2
0x2da00  ldc.i4.4
0x2da01  bne.un.s loc_2DA45
0x2da03  ldloc.s  4
0x2da05  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2da0a  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2da0f  brfalse.s loc_2DA17
0x2da11  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidReportLinkException::.ctor()
0x2da16  throw
0x2da17  ldloc.1
0x2da18  ldloc.s  4
0x2da1a  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.DBInterface::GetPathById(valuetype [mscorlib]System.Guid id)
0x2da1f  stloc.s  9
0x2da21  ldloc.s  9
0x2da23  call     bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::IsNullOrEmpty(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase)
0x2da28  brfalse.s loc_2DA30
0x2da2a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidReportLinkException::.ctor()
0x2da2f  throw
0x2da30  ldarg.0
0x2da31  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.DefinitionLoader::m_service
0x2da36  ldloc.s  9
0x2da38  ldstr    aRepublishingpa// "RepublishingPath"
0x2da3d  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath, string)
0x2da42  stloc.0
0x2da43  br.s     loc_2DA4C
0x2da45  ldarg.0
0x2da46  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.DefinitionLoader::get_ItemContext()
0x2da4b  stloc.0
0x2da4c  ldloc.0
0x2da4d  ret
```
