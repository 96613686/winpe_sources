# Microsoft.ReportingServices.Diagnostics.Globals::InitServerWithoutDumperInner

- ea: `0xa8e0`
- end: `0xa921`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::InitServerWithoutDumperInner`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa820`
- `0xa8b0`

## callees

- `0xa8e0`
- `0xa930`
- `0xa960`

## string_xrefs

- `0xa8ed`: `Configuration is not initialized.`

## pseudocode

```c

```

## disassembly

```asm
0xa8e0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0xa8e5  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xa8ea  ldnull
0xa8eb  cgt.un
0xa8ed  ldstr    aConfigurationI// "Configuration is not initialized."
0xa8f2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xa8f7  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xa8fc  stloc.0
0xa8fd  ldloc.0
0xa8fe  ldc.i4.1
0xa8ff  ble.un.s loc_A907
0xa901  ldloc.0
0xa902  ldc.i4.3
0xa903  sub
0xa904  ldc.i4.2
0xa905  bgt.un.s loc_A920
0xa907  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0xa90c  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.NativeRSEventLogProvider::.ctor()
0xa911  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::Init(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventLogProvider)
0xa916  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_Current()
0xa91b  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::EnsureTraceInitializedCorrectly()
0xa920  ret
```
