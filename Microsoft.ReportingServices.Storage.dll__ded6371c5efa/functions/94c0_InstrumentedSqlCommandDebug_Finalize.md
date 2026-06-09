# InstrumentedSqlCommandDebug::Finalize

- ea: `0x94c0`
- end: `0x94da`
- name: `InstrumentedSqlCommandDebug::Finalize`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x94c0`

## string_xrefs

- `0x94c6`: `Detected finalization of InstrumentedSqlCommandDebug. This is an error condition and should never happen`

## pseudocode

```c

```

## disassembly

```asm
0x94c0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x94c5  ldc.i4.1
0x94c6  ldstr    aDetectedFinali_0// "Detected finalization of InstrumentedSq"...
0x94cb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x94d0  leave.s  loc_94D9
0x94d2  ldarg.0
0x94d3  call     instance void [mscorlib]System.Object::Finalize()
0x94d8  endfinally
0x94d9  ret
```
