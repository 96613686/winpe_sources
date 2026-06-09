# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.ComponentUtils::IsSupportedReportItem

- ea: `0xd60`
- end: `0xd9a`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.ComponentUtils::IsSupportedReportItem`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x990`

## callees

- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.0
0xd61  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle
0xd66  brfalse.s loc_D7E
0xd68  ldarg.0
0xd69  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle
0xd6e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle::get_ReportItems()
0xd73  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::get_Count()
0xd78  brtrue.s loc_D7C
0xd7a  ldc.i4.0
0xd7b  ret
0xd7c  ldc.i4.1
0xd7d  ret
0xd7e  ldarg.0
0xd7f  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataRegion
0xd84  brtrue.s loc_D96
0xd86  ldarg.0
0xd87  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Image
0xd8c  brtrue.s loc_D96
0xd8e  ldarg.0
0xd8f  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Map
0xd94  brfalse.s loc_D98
0xd96  ldc.i4.1
0xd97  ret
0xd98  ldc.i4.0
0xd99  ret
```
