# Microsoft.ReportingServices.Library.KeyStorage::ValidateScaleoutEdition

- ea: `0x2f00`
- end: `0x2f37`
- name: `Microsoft.ReportingServices.Library.KeyStorage::ValidateScaleoutEdition`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3420`

## callees

- `0x2f00`
- `0x2f40`

## pseudocode

```c

```

## disassembly

```asm
0x2f00  ldarg.0
0x2f01  call     instance int32 Microsoft.ReportingServices.Library.KeyStorage::GetKeyCount()
0x2f06  ldc.i4.1
0x2f07  ble.s    loc_2F36
0x2f09  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x2f0e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x2f13  brfalse.s loc_2F25
0x2f15  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x2f1a  ldc.i4.3
0x2f1b  ldstr    aPerformingSkuV_0// "Performing sku validation : scale-out"
0x2f20  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2f25  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2f2a  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x2f2f  ldc.i4.s 0xB
0x2f31  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::ThrowIfFeatureNotEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x2f36  ret
```
