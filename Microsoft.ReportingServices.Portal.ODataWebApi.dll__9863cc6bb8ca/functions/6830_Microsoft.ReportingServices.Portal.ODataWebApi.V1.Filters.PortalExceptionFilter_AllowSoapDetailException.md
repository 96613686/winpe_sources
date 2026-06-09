# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AllowSoapDetailException

- ea: `0x6830`
- end: `0x6848`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AllowSoapDetailException`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1920`
- `0xcc00`

## callees

- `0x6810`

## pseudocode

```c

```

## disassembly

```asm
0x6830  ldarg.0
0x6831  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x6836  ldarg.1
0x6837  call     string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::GetSoapDetailDataName(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code)
0x683c  ldc.i4.1
0x683d  box      [mscorlib]System.Boolean
0x6842  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x6847  ret
```
