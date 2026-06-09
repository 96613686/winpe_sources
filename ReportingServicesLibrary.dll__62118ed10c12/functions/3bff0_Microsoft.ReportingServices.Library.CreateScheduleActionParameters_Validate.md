# Microsoft.ReportingServices.Library.CreateScheduleActionParameters::Validate

- ea: `0x3bff0`
- end: `0x3c057`
- name: `Microsoft.ReportingServices.Library.CreateScheduleActionParameters::Validate`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x3bf00`
- `0x3bf30`
- `0x3bff0`
- `0x723c0`

## string_xrefs

- `0x3c033`: `ScheduleDefinition`
- `0x3c04b`: `ScheduleDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x3bff0  ldarg.0
0x3bff1  call     instance string Microsoft.ReportingServices.Library.CreateScheduleActionParameters::get_Name()
0x3bff6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bffb  brfalse.s loc_3C008
0x3bffd  ldstr    aName// "Name"
0x3c002  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x3c007  throw
0x3c008  ldarg.0
0x3c009  call     instance string Microsoft.ReportingServices.Library.CreateScheduleActionParameters::get_Name()
0x3c00e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3c013  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::get_MaxItemNameLength()
0x3c018  ble.s    loc_3C02B
0x3c01a  ldarg.0
0x3c01b  call     instance string Microsoft.ReportingServices.Library.CreateScheduleActionParameters::get_Name()
0x3c020  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::get_MaxItemNameLength()
0x3c025  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemNameException::.ctor(string, int32)
0x3c02a  throw
0x3c02b  ldarg.0
0x3c02c  call     instance class Microsoft.ReportingServices.Library.Soap.ScheduleDefinition Microsoft.ReportingServices.Library.CreateScheduleActionParameters::get_ScheduleDefinition()
0x3c031  brtrue.s loc_3C03E
0x3c033  ldstr    aScheduledefini// "ScheduleDefinition"
0x3c038  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x3c03d  throw
0x3c03e  ldarg.0
0x3c03f  call     instance class Microsoft.ReportingServices.Library.Soap.ScheduleDefinition Microsoft.ReportingServices.Library.CreateScheduleActionParameters::get_ScheduleDefinition()
0x3c044  callvirt instance bool Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::IsValid()
0x3c049  brtrue.s loc_3C056
0x3c04b  ldstr    aScheduledefini// "ScheduleDefinition"
0x3c050  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x3c055  throw
0x3c056  ret
```
