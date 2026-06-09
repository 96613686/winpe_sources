# Microsoft.ReportingServices.Library.Storage::set_ConnectionManager

- ea: `0x6a50`
- end: `0x6a70`
- name: `Microsoft.ReportingServices.Library.Storage::set_ConnectionManager`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e0`
- `0x2850`

## callees

- `0x6a50`

## string_xrefs

- `0x6a5e`: `Connection manager already initialized`

## pseudocode

```c

```

## disassembly

```asm
0x6a50  ldarg.0
0x6a51  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6a56  brfalse.s loc_6A68
0x6a58  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6a5d  ldc.i4.0
0x6a5e  ldstr    aConnectionMana// "Connection manager already initialized"
0x6a63  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6a68  ldarg.0
0x6a69  ldarg.1
0x6a6a  stfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6a6f  ret
```
