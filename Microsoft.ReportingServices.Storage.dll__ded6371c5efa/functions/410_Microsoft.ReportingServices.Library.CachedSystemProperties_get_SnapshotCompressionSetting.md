# Microsoft.ReportingServices.Library.CachedSystemProperties::get_SnapshotCompressionSetting

- ea: `0x410`
- end: `0x45b`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_SnapshotCompressionSetting`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x410`

## string_xrefs

- `0x421`: `SnapshotCompression`
- `0x42b`: `SnapshotCompression`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SnapshotCompressionFlags> Microsoft.ReportingServices.Library.CachedSystemProperties::m_SnapshotCompressionSettingParam
0x415  brtrue.s loc_450
0x417  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x41c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x421  ldstr    aSnapshotcompre// "SnapshotCompression"
0x426  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x42b  ldstr    aSnapshotcompre// "SnapshotCompression"
0x430  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x435  ldc.i4.1
0x436  ldstr    asc_A0B2// ""
0x43b  newobj   instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SnapshotCompressionFlags>::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, var<u1>, !!T0)
0x440  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SnapshotCompressionFlags> Microsoft.ReportingServices.Library.CachedSystemProperties::m_SnapshotCompressionSettingParam
0x445  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SnapshotCompressionFlags> Microsoft.ReportingServices.Library.CachedSystemProperties::m_SnapshotCompressionSettingParam
0x44a  ldc.i4.1
0x44b  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x450  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SnapshotCompressionFlags> Microsoft.ReportingServices.Library.CachedSystemProperties::m_SnapshotCompressionSettingParam
0x455  callvirt instance var<u1> class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SnapshotCompressionFlags>::get_Value()
0x45a  ret
```
