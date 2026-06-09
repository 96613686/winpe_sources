# Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::Validate

- ea: `0x3c6a0`
- end: `0x3c71f`
- name: `Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::Validate`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x3c5d0`
- `0x3c600`
- `0x3c630`
- `0x3c6a0`
- `0x723c0`

## string_xrefs

- `0x3c6fb`: `ScheduleDefinition`
- `0x3c713`: `ScheduleDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x3c6a0  ldarg.0
0x3c6a1  call     instance string Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::get_Name()
0x3c6a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3c6ab  brfalse.s loc_3C6B8
0x3c6ad  ldstr    aName// "Name"
0x3c6b2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x3c6b7  throw
0x3c6b8  ldarg.0
0x3c6b9  call     instance string Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::get_Name()
0x3c6be  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3c6c3  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::get_MaxItemNameLength()
0x3c6c8  ble.s    loc_3C6DB
0x3c6ca  ldarg.0
0x3c6cb  call     instance string Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::get_Name()
0x3c6d0  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::get_MaxItemNameLength()
0x3c6d5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemNameException::.ctor(string, int32)
0x3c6da  throw
0x3c6db  ldarg.0
0x3c6dc  call     instance string Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::get_ScheduleID()
0x3c6e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3c6e6  brfalse.s loc_3C6F3
0x3c6e8  ldstr    aScheduleid_0// "ScheduleID"
0x3c6ed  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x3c6f2  throw
0x3c6f3  ldarg.0
0x3c6f4  call     instance class Microsoft.ReportingServices.Library.Soap.ScheduleDefinition Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::get_ScheduleDefinition()
0x3c6f9  brtrue.s loc_3C706
0x3c6fb  ldstr    aScheduledefini// "ScheduleDefinition"
0x3c700  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x3c705  throw
0x3c706  ldarg.0
0x3c707  call     instance class Microsoft.ReportingServices.Library.Soap.ScheduleDefinition Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters::get_ScheduleDefinition()
0x3c70c  callvirt instance bool Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::IsValid()
0x3c711  brtrue.s loc_3C71E
0x3c713  ldstr    aScheduledefini// "ScheduleDefinition"
0x3c718  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x3c71d  throw
0x3c71e  ret
```
