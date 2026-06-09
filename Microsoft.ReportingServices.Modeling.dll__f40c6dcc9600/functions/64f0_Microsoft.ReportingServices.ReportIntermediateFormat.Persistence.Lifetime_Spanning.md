# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime::Spanning

- ea: `0x64f0`
- end: `0x6531`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime::Spanning`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xf60`
- `0x6410`

## string_xrefs

- `0x650c`: `Invalid removedVersion`
- `0x651f`: `removedVersion must be later than addedVersion`

## pseudocode

```c

```

## disassembly

```asm
0x64f0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x64f5  ldarg.0
0x64f6  ldc.i4.0
0x64f7  cgt
0x64f9  ldstr    aInvalidAddedve// "Invalid addedVersion"
0x64fe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6503  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x6508  ldarg.1
0x6509  ldc.i4.0
0x650a  cgt
0x650c  ldstr    aInvalidRemoved// "Invalid removedVersion"
0x6511  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6516  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x651b  ldarg.1
0x651c  ldarg.0
0x651d  cgt
0x651f  ldstr    aRemovedversion// "removedVersion must be later than added"...
0x6524  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6529  ldarg.0
0x652a  ldarg.1
0x652b  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime::.ctor(int32 addedVersion, int32 removedVersion)
0x6530  ret
```
