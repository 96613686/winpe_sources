# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RsErrorCodeMapperUtility::get_HttpStatusCodeMap

- ea: `0xb1c0`
- end: `0xb1d5`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RsErrorCodeMapperUtility::get_HttpStatusCodeMap`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6850`

## callees

- `0xb1c0`
- `0xb1e0`

## pseudocode

```c

```

## disassembly

```asm
0xb1c0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, valuetype [System]System.Net.HttpStatusCode> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RsErrorCodeMapperUtility::_httpStatusCodeMap
0xb1c5  dup
0xb1c6  brtrue.s loc_B1D4
0xb1c8  pop
0xb1c9  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, valuetype [System]System.Net.HttpStatusCode> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RsErrorCodeMapperUtility::BuildDictionary()
0xb1ce  dup
0xb1cf  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, valuetype [System]System.Net.HttpStatusCode> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RsErrorCodeMapperUtility::_httpStatusCodeMap
0xb1d4  ret
```
