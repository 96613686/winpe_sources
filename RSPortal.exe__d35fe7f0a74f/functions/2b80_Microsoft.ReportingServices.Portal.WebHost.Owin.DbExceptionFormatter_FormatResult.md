# Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::FormatResult

- ea: `0x2b80`
- end: `0x2baf`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::FormatResult`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x2b80  ldarg.0
0x2b81  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2b86  ldc.i4   0x1F7
0x2b8b  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x2b90  ldarg.0
0x2b91  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2b96  ldarg.1
0x2b97  ldarg.2
0x2b98  ldc.i4.1
0x2b99  newobj   instance void [System.Web.Http]System.Web.Http.HttpError::.ctor(class [mscorlib]System.Exception, bool)
0x2b9e  newobj   instance void class <>f__AnonymousType0`2<int32, class [System.Web.Http]System.Web.Http.HttpError>::.ctor(var<u1>, !!T0)
0x2ba3  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x2ba8  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.IOwinResponse::WriteAsync(string)
0x2bad  pop
0x2bae  ret
```
