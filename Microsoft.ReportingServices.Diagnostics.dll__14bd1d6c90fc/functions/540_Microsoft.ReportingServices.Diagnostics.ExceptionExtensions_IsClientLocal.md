# Microsoft.ReportingServices.Diagnostics.ExceptionExtensions::IsClientLocal

- ea: `0x540`
- end: `0x595`
- name: `Microsoft.ReportingServices.Diagnostics.ExceptionExtensions::IsClientLocal`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x4f0`

## callees

- `0x540`

## string_xrefs

- `0x549`: `ReportingServices.IsLocalRequest`

## pseudocode

```c

```

## disassembly

```asm
0x540  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x545  stloc.0
0x546  ldloc.0
0x547  brtrue.s loc_56C
0x549  ldstr    aReportingservi// "ReportingServices.IsLocalRequest"
0x54e  call     object [mscorlib]System.Runtime.Remoting.Messaging.CallContext::GetData(string)
0x553  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x558  stloc.1
0x559  ldloca.s 1
0x55b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x560  brtrue.s loc_564
0x562  ldc.i4.1
0x563  ret
0x564  ldloca.s 1
0x566  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x56b  ret
0x56c  ldloc.0
0x56d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x572  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsLocal()
0x577  stloc.2
0x578  ldloc.0
0x579  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x57e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x583  ldstr    aRsclientnotloc// "RSClientNotLocalHeader"
0x588  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x58d  ldnull
0x58e  ceq
0x590  stloc.3
0x591  ldloc.2
0x592  ldloc.3
0x593  and
0x594  ret
```
