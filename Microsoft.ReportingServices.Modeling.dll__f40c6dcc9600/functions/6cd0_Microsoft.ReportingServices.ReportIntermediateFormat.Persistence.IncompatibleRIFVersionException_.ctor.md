# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IncompatibleRIFVersionException::.ctor

- ea: `0x6cd0`
- end: `0x6d03`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IncompatibleRIFVersionException::.ctor`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d20`

## callees

- `0xf60`

## string_xrefs

- `0x6cdb`: `The RIF document is not compatible with this code version.  Document Version: {0} Code Version: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x6cd0  ldarg.0
0x6cd1  ldc.i4   0x12D
0x6cd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cdb  ldstr    aTheRifDocument// "The RIF document is not compatible with"...
0x6ce0  ldarg.1
0x6ce1  box      [mscorlib]System.Int32
0x6ce6  ldarg.2
0x6ce7  box      [mscorlib]System.Int32
0x6cec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x6cf1  ldnull
0x6cf2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x6cf7  ldnull
0x6cf8  call     T0x2B00001C
0x6cfd  call     instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, string, class [mscorlib]System.Exception, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, object[])
0x6d02  ret
```
