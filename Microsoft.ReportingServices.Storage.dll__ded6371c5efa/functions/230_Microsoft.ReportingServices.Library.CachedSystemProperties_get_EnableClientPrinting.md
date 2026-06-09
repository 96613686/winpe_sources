# Microsoft.ReportingServices.Library.CachedSystemProperties::get_EnableClientPrinting

- ea: `0x230`
- end: `0x27f`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_EnableClientPrinting`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x230`

## pseudocode

```c

```

## disassembly

```asm
0x230  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableClientPrintingParam
0x235  brtrue.s loc_274
0x237  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x23c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x241  ldstr    aEnableclientpr// "EnableClientPrinting"
0x246  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x24b  ldstr    aEnableclientpr// "EnableClientPrinting"
0x250  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x255  ldsfld   bool Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultEnableClientPrinting
0x25a  ldstr    asc_A0B2// ""
0x25f  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, bool, string)
0x264  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableClientPrintingParam
0x269  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableClientPrintingParam
0x26e  ldc.i4.1
0x26f  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x274  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableClientPrintingParam
0x279  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::get_Value()
0x27e  ret
```
