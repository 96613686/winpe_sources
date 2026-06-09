# Microsoft.ReportingServices.Library.RSSoapAction`1::TraceOutput

- ea: `0x1f0c0`
- end: `0x1f124`
- name: `Microsoft.ReportingServices.Library.RSSoapAction`1::TraceOutput`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ee40`
- `0x1f0c0`

## string_xrefs

- `0x1f0e2`: `Call to {0} completed. Returns {1}.`
- `0x1f10a`: `Call to {0} completed.`

## pseudocode

```c

```

## disassembly

```asm
0x1f0c0  ldarg.0
0x1f0c1  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f0c6  box      var<u1>
0x1f0cb  callvirt instance string Microsoft.ReportingServices.Library.RSSoapActionParameters::get_OutputTrace()
0x1f0d0  stloc.0
0x1f0d1  ldloc.0
0x1f0d2  brfalse.s loc_1F105
0x1f0d4  ldloc.0
0x1f0d5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1f0da  ldc.i4.0
0x1f0db  ble.s    loc_1F105
0x1f0dd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x1f0e2  ldstr    aCallTo0Complet// "Call to {0} completed. Returns {1}."
0x1f0e7  ldc.i4.2
0x1f0e8  newarr   [mscorlib]System.Object
0x1f0ed  dup
0x1f0ee  ldc.i4.0
0x1f0ef  ldarg.0
0x1f0f0  call     instance string class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionName()
0x1f0f5  stelem.ref
0x1f0f6  dup
0x1f0f7  ldc.i4.1
0x1f0f8  ldloc.0
0x1f0f9  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.StringUtils::RemoveControlAndNonSpacesWhitespaceCharacters(string)
0x1f0fe  stelem.ref
0x1f0ff  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x1f104  ret
0x1f105  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x1f10a  ldstr    aCallTo0Complet_0// "Call to {0} completed."
0x1f10f  ldc.i4.1
0x1f110  newarr   [mscorlib]System.Object
0x1f115  dup
0x1f116  ldc.i4.0
0x1f117  ldarg.0
0x1f118  call     instance string class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionName()
0x1f11d  stelem.ref
0x1f11e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x1f123  ret
```
