# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateItem

- ea: `0x2530`
- end: `0x279e`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateItem`
- size: `622`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x2500`
- `0x2520`

## callees

- `0x2200`
- `0x2530`
- `0x2850`
- `0x2950`
- `0x3510`
- `0x37a0`
- `0x38d0`
- `0x3c20`
- `0x3e40`
- `0x4e10`
- `0x5040`
- `0x51f0`
- `0x5390`
- `0x9e80`

## string_xrefs

- `0x25e5`: `Folder created`
- `0x260c`: `Kpi created`
- `0x2649`: `LinkedReport created`
- `0x2678`: `Report created`
- `0x26a2`: `PowerBI Report created`
- `0x26cb`: `ExcelWorkbook created`
- `0x26f2`: `DataSource created`
- `0x2721`: `DataSet created`
- `0x2748`: `Resource created`
- `0x278b`: `Component created`

## pseudocode

```c

```

## disassembly

```asm
0x2530  ldarg.0
0x2531  ldarg.2
0x2532  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x2537  ldarg.2
0x2538  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x253d  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType type, string path)
0x2542  ldarg.0
0x2543  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_fileSizeRestrictions
0x2548  ldarg.2
0x2549  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x254e  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions::ThrowIfSizeIsOutOfLimits(unsigned int8[])
0x2553  ldarg.1
0x2554  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x2559  stloc.0
0x255a  ldarg.2
0x255b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::ComputeParentPath()
0x2560  stloc.1
0x2561  ldarg.0
0x2562  ldloc.0
0x2563  ldloc.1
0x2564  ldarg.2
0x2565  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemCanBeCreated(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string parentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x256a  ldc.i4.0
0x256b  stloc.2
0x256c  ldnull
0x256d  stloc.3
0x256e  ldarg.2
0x256f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x2574  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::get_Count()
0x2579  ldc.i4.0
0x257a  ble.s    loc_2588
0x257c  ldarg.2
0x257d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x2582  call     T0x2B000020
0x2587  stloc.3
0x2588  ldarg.2
0x2589  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x258e  stloc.s  4
0x2590  ldloc.s  4
0x2592  ldc.i4.1
0x2593  sub
0x2594  switch   loc_25CE, loc_2658, loc_26DA, loc_2701, loc_276B, loc_272D, loc_25F4, loc_261B, loc_2632, loc_2754, loc_2687, loc_26B1
0x25c9  br       loc_2797
0x25ce  ldarg.3
0x25cf  ldarg.0
0x25d0  ldarg.1
0x25d1  ldloc.1
0x25d2  ldarg.2
0x25d3  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x25d8  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateFolder(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string parentPath, string folderName)
0x25dd  stind.ref
0x25de  ldarg.0
0x25df  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x25e4  ldc.i4.3
0x25e5  ldstr    aFolderCreated// "Folder created"
0x25ea  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x25ef  br       loc_279C
0x25f4  ldarg.3
0x25f5  ldarg.0
0x25f6  ldloc.0
0x25f7  ldarg.1
0x25f8  ldloc.1
0x25f9  ldarg.2
0x25fa  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi
0x25ff  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateKpi(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string parentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi item)
0x2604  stind.ref
0x2605  ldarg.0
0x2606  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x260b  ldc.i4.3
0x260c  ldstr    aKpiCreated// "Kpi created"
0x2611  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2616  br       loc_279C
0x261b  ldarg.0
0x261c  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x2621  ldc.i4.3
0x2622  ldstr    aMobileReportCr// "Mobile Report creation is not supported"...
0x2627  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x262c  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x2631  throw
0x2632  ldarg.3
0x2633  ldarg.0
0x2634  ldloc.0
0x2635  ldarg.1
0x2636  ldarg.2
0x2637  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport
0x263c  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateLinkedReport(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport linkedReport)
0x2641  stind.ref
0x2642  ldarg.0
0x2643  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x2648  ldc.i4.3
0x2649  ldstr    aLinkedreportCr// "LinkedReport created"
0x264e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2653  br       loc_279C
0x2658  ldarg.3
0x2659  ldarg.0
0x265a  ldloc.0
0x265b  ldarg.1
0x265c  ldarg.2
0x265d  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2662  ldloc.1
0x2663  ldloc.2
0x2664  ldarg.2
0x2665  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x266a  ldloc.3
0x266b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateReport(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string reportName, string parentFolder, bool overwrite, unsigned int8[] definition, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[] properties)
0x2670  stind.ref
0x2671  ldarg.0
0x2672  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x2677  ldc.i4.3
0x2678  ldstr    aReportCreated// "Report created"
0x267d  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2682  br       loc_279C
0x2687  ldarg.0
0x2688  ldloc.0
0x2689  ldarg.1
0x268a  ldloc.1
0x268b  ldloc.2
0x268c  ldarg.2
0x268d  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport
0x2692  ldloc.3
0x2693  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreatePowerBIReport(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string parentPath, bool overwrite, class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport item, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[] properties)
0x2698  ldarg.3
0x2699  ldarg.2
0x269a  stind.ref
0x269b  ldarg.0
0x269c  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x26a1  ldc.i4.3
0x26a2  ldstr    aPowerbiReportC// "PowerBI Report created"
0x26a7  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x26ac  br       loc_279C
0x26b1  ldarg.3
0x26b2  ldarg.0
0x26b3  ldloc.0
0x26b4  ldarg.1
0x26b5  ldloc.1
0x26b6  ldloc.2
0x26b7  ldarg.2
0x26b8  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook
0x26bd  ldloc.3
0x26be  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateExcel(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string parentPath, bool overwrite, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook item, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[] properties)
0x26c3  stind.ref
0x26c4  ldarg.0
0x26c5  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x26ca  ldc.i4.3
0x26cb  ldstr    aExcelworkbookC// "ExcelWorkbook created"
0x26d0  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x26d5  br       loc_279C
0x26da  ldarg.3
0x26db  ldarg.0
0x26dc  ldloc.0
0x26dd  ldarg.1
0x26de  ldloc.1
0x26df  ldarg.2
0x26e0  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource
0x26e5  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateDataSource(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string parentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0x26ea  stind.ref
0x26eb  ldarg.0
0x26ec  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x26f1  ldc.i4.3
0x26f2  ldstr    aDatasourceCrea// "DataSource created"
0x26f7  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x26fc  br       loc_279C
0x2701  ldarg.3
0x2702  ldarg.0
0x2703  ldloc.0
0x2704  ldarg.1
0x2705  ldarg.2
0x2706  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x270b  ldloc.1
0x270c  ldloc.2
0x270d  ldarg.2
0x270e  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x2713  ldloc.3
0x2714  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateDataSet(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string dataSetName, string parentFolder, bool overwrite, unsigned int8[] definition, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[] properties)
0x2719  stind.ref
0x271a  ldarg.0
0x271b  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x2720  ldc.i4.3
0x2721  ldstr    aDatasetCreated// "DataSet created"
0x2726  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x272b  br.s     loc_279C
0x272d  ldarg.3
0x272e  ldarg.0
0x272f  ldloc.0
0x2730  ldarg.1
0x2731  ldarg.2
0x2732  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2737  ldloc.1
0x2738  ldloc.2
0x2739  ldarg.2
0x273a  ldloc.3
0x273b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Resource Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateResource(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string resourceName, string parentFolder, bool overwrite, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[] properties)
0x2740  stind.ref
0x2741  ldarg.0
0x2742  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x2747  ldc.i4.3
0x2748  ldstr    aResourceCreate// "Resource created"
0x274d  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2752  br.s     loc_279C
0x2754  ldarg.0
0x2755  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x275a  ldc.i4.3
0x275b  ldstr    aReportmodelCre// "ReportModel creation is not supported."
0x2760  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2765  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x276a  throw
0x276b  ldarg.3
0x276c  ldarg.0
0x276d  ldloc.0
0x276e  ldarg.1
0x276f  ldarg.2
0x2770  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2775  ldloc.1
0x2776  ldloc.2
0x2777  ldarg.2
0x2778  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x277d  ldloc.3
0x277e  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateComponent(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string componentName, string parentFolder, bool overwrite, unsigned int8[] definition, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[] properties)
0x2783  stind.ref
0x2784  ldarg.0
0x2785  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x278a  ldc.i4.3
0x278b  ldstr    aComponentCreat// "Component created"
0x2790  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2795  br.s     loc_279C
0x2797  ldarg.3
0x2798  ldnull
0x2799  stind.ref
0x279a  ldc.i4.0
0x279b  ret
0x279c  ldc.i4.1
0x279d  ret
```
