# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateReport

- ea: `0x3510`
- end: `0x35a6`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateReport`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x3510`

## pseudocode

```c

```

## disassembly

```asm
0x3510  ldarg.3
0x3511  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3516  brfalse.s loc_3523
0x3518  ldstr    aReportname// "reportName"
0x351d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3522  throw
0x3523  ldarg.3
0x3524  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x3529  ldstr    aRdl_0// ".RDL"
0x352e  ldc.i4.5
0x352f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3534  brfalse.s loc_353E
0x3536  ldarg.3
0x3537  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x353c  starg.s  3
0x353e  ldnull
0x353f  stloc.0
0x3540  ldarg.s  7
0x3542  brfalse.s loc_3575
0x3544  ldarg.s  7
0x3546  ldlen
0x3547  brfalse.s loc_3575
0x3549  ldarg.s  7
0x354b  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property> <>c::<>9__75_0
0x3550  dup
0x3551  brtrue.s loc_356A
0x3553  pop
0x3554  ldsfld   class <>c <>c::<>9
0x3559  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property <>c::<CreateReport>b__75_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property prop)
0x355f  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property>::.ctor(object, native int)
0x3564  dup
0x3565  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property> <>c::<>9__75_0
0x356a  call     T0x2B00002A
0x356f  call     T0x2B00002B
0x3574  stloc.0
0x3575  ldarg.0
0x3576  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_soapRS2010Proxy
0x357b  ldarg.2
0x357c  ldstr    aReport_0// "Report"
0x3581  ldarg.3
0x3582  ldarg.s  4
0x3584  ldarg.s  5
0x3586  ldarg.s  6
0x3588  ldloc.0
0x3589  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::CreateCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string, string, string, bool, unsigned int8[], class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[])
0x358e  pop
0x358f  ldarg.0
0x3590  ldarg.1
0x3591  ldarg.2
0x3592  ldarg.0
0x3593  ldarg.s  4
0x3595  ldarg.3
0x3596  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x359b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x35a0  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.Report
0x35a5  ret
```
