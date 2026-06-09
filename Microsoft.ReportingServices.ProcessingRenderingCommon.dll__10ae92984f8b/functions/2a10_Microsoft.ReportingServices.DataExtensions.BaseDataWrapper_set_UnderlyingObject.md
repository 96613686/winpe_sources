# Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::set_UnderlyingObject

- ea: `0x2a10`
- end: `0x2a30`
- name: `Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::set_UnderlyingObject`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x2a1e`: `Should never replace the underlying connection`

## pseudocode

```c

```

## disassembly

```asm
0x2a10  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x2a15  ldarg.0
0x2a16  ldfld    object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::m_underlyingObject
0x2a1b  ldnull
0x2a1c  ceq
0x2a1e  ldstr    aShouldNeverRep// "Should never replace the underlying con"...
0x2a23  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2a28  ldarg.0
0x2a29  ldarg.1
0x2a2a  stfld    object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::m_underlyingObject
0x2a2f  ret
```
