# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_BlankImageUrl

- ea: `0x1ef0`
- end: `0x1f27`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_BlankImageUrl`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x20e0`

## pseudocode

```c

```

## disassembly

```asm
0x1ef0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1ef5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1efa  stloc.0
0x1efb  ldloc.0
0x1efc  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1f01  ldc.i4.1
0x1f02  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x1f07  newobj   instance void [System]System.Uri::.ctor(string)
0x1f0c  ldloc.0
0x1f0d  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x1f12  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x1f17  callvirt instance string [mscorlib]System.Object::ToString()
0x1f1c  ldstr    aImagesBlankGif// "/images/blank.gif"
0x1f21  call     string [mscorlib]System.String::Concat(string, string)
0x1f26  ret
```
