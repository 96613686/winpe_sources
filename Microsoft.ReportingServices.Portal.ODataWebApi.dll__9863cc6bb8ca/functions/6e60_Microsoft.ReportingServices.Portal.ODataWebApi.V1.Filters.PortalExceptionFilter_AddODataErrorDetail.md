# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail

- ea: `0x6e60`
- end: `0x6e85`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6850`
- `0x6bb0`
- `0x6da0`

## callees

- `0x6e60`

## pseudocode

```c

```

## disassembly

```asm
0x6e60  ldarg.1
0x6e61  ldind.ref
0x6e62  ldarg.1
0x6e63  ldind.ref
0x6e64  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail> [Microsoft.OData.Core]Microsoft.OData.ODataError::get_Details()
0x6e69  dup
0x6e6a  brtrue.s loc_6E72
0x6e6c  pop
0x6e6d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail>::.ctor()
0x6e72  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Details(class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail>)
0x6e77  ldarg.1
0x6e78  ldind.ref
0x6e79  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail> [Microsoft.OData.Core]Microsoft.OData.ODataError::get_Details()
0x6e7e  ldarg.0
0x6e7f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail>::Add(var<u1>)
0x6e84  ret
```
