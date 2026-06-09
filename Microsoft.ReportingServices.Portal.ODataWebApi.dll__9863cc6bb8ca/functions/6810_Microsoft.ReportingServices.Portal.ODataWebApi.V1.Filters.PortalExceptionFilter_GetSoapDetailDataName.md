# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::GetSoapDetailDataName

- ea: `0x6810`
- end: `0x6821`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::GetSoapDetailDataName`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1910`
- `0x6830`
- `0x6850`

## pseudocode

```c

```

## disassembly

```asm
0x6810  ldstr    aShowdetailof0// "ShowDetailOf({0})"
0x6815  ldarg.0
0x6816  box      [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode
0x681b  call     string [mscorlib]System.String::Format(string, object)
0x6820  ret
```
