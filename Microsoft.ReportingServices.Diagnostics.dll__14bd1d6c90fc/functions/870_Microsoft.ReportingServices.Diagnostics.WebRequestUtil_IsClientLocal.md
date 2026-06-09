# Microsoft.ReportingServices.Diagnostics.WebRequestUtil::IsClientLocal

- ea: `0x870`
- end: `0x8c5`
- name: `Microsoft.ReportingServices.Diagnostics.WebRequestUtil::IsClientLocal`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8d0`
- `0x8e0`

## callees

- `0x5b0`
- `0x870`

## string_xrefs

- `0x879`: `ReportingServices.IsLocalRequest`

## pseudocode

```c

```

## disassembly

```asm
0x870  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x875  stloc.0
0x876  ldloc.0
0x877  brtrue.s loc_89C
0x879  ldstr    aReportingservi// "ReportingServices.IsLocalRequest"
0x87e  call     object [mscorlib]System.Runtime.Remoting.Messaging.CallContext::GetData(string)
0x883  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x888  stloc.1
0x889  ldloca.s 1
0x88b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x890  brtrue.s loc_894
0x892  ldc.i4.1
0x893  ret
0x894  ldloca.s 1
0x896  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x89b  ret
0x89c  ldloc.0
0x89d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8a2  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsLocal()
0x8a7  stloc.2
0x8a8  ldloc.0
0x8a9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8ae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x8b3  call     string Microsoft.ReportingServices.Diagnostics.LocalClientConstants::get_ClientNotLocalHeaderName()
0x8b8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8bd  ldnull
0x8be  ceq
0x8c0  stloc.3
0x8c1  ldloc.2
0x8c2  ldloc.3
0x8c3  and
0x8c4  ret
```
