# CancelableSqlCommandDebug::Finalize

- ea: `0x9460`
- end: `0x947a`
- name: `CancelableSqlCommandDebug::Finalize`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x9460`

## string_xrefs

- `0x9466`: `Detected finalization of CancelableSqlCommandDebug. This is an error condition and should never happen`

## pseudocode

```c

```

## disassembly

```asm
0x9460  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9465  ldc.i4.1
0x9466  ldstr    aDetectedFinali// "Detected finalization of CancelableSqlC"...
0x946b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9470  leave.s  loc_9479
0x9472  ldarg.0
0x9473  call     instance void [mscorlib]System.Object::Finalize()
0x9478  endfinally
0x9479  ret
```
