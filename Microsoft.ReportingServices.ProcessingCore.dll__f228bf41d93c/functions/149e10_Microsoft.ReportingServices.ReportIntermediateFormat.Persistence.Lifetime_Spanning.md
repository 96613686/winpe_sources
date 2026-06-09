# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime::Spanning

- ea: `0x149e10`
- end: `0x149e51`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime::Spanning`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11a590`

## callees

- `0x149d30`

## string_xrefs

- `0x149e2c`: `Invalid removedVersion`
- `0x149e3f`: `removedVersion must be later than addedVersion`

## pseudocode

```c

```

## disassembly

```asm
0x149e10  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x149e15  ldarg.0
0x149e16  ldc.i4.0
0x149e17  cgt
0x149e19  ldstr    aInvalidAddedve// "Invalid addedVersion"
0x149e1e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x149e23  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x149e28  ldarg.1
0x149e29  ldc.i4.0
0x149e2a  cgt
0x149e2c  ldstr    aInvalidRemoved// "Invalid removedVersion"
0x149e31  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x149e36  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x149e3b  ldarg.1
0x149e3c  ldarg.0
0x149e3d  cgt
0x149e3f  ldstr    aRemovedversion// "removedVersion must be later than added"...
0x149e44  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x149e49  ldarg.0
0x149e4a  ldarg.1
0x149e4b  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime::.ctor(int32 addedVersion, int32 removedVersion)
0x149e50  ret
```
