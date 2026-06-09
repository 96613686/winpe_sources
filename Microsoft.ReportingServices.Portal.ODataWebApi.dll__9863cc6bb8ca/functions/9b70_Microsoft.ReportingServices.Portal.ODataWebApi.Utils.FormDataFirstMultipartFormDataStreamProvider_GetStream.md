# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetStream

- ea: `0x9b70`
- end: `0x9c58`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetStream`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x9b70`
- `0x9c70`
- `0x9c90`
- `0x9cd0`
- `0x9d10`
- `0xefb0`

## pseudocode

```c

```

## disassembly

```asm
0x9b70  ldarg.2
0x9b71  callvirt instance class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentDisposition()
0x9b76  brfalse  loc_9C56
0x9b7b  ldarg.0
0x9b7c  ldarg.0
0x9b7d  call     instance class [System]System.Collections.Specialized.NameValueCollection [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::get_FormData()
0x9b82  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::SaveValueToResult(class [System]System.Collections.Specialized.NameValueCollection formData)
0x9b87  ldarg.0
0x9b88  ldarg.2
0x9b89  ldarg.0
0x9b8a  call     instance class [System]System.Collections.Specialized.NameValueCollection [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::get_FormData()
0x9b8f  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::SaveNameToResult(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders headers, class [System]System.Collections.Specialized.NameValueCollection formData)
0x9b94  ldarg.0
0x9b95  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::_lastFormKey
0x9b9a  ldstr    aFile// "File"
0x9b9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9ba4  brfalse  loc_9C4F
0x9ba9  ldarg.0
0x9baa  call     instance class [System]System.Collections.Specialized.NameValueCollection [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::get_FormData()
0x9baf  ldstr    aSize// "Size"
0x9bb4  ldarg.0
0x9bb5  ldarg.1
0x9bb6  ldarg.2
0x9bb7  callvirt instance class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentType()
0x9bbc  call     instance int64 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetFileSize(class [System.Net.Http]System.Net.Http.HttpContent content, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType)
0x9bc1  stloc.0
0x9bc2  ldloca.s 0
0x9bc4  call     instance string [mscorlib]System.Int64::ToString()
0x9bc9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x9bce  ldarg.0
0x9bcf  ldfld    class FormDataAvailableHandler Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::FormDataAvailable
0x9bd4  brfalse.s loc_9BE5
0x9bd6  ldarg.0
0x9bd7  ldfld    class FormDataAvailableHandler Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::FormDataAvailable
0x9bdc  callvirt instance bool FormDataAvailableHandler::Invoke()
0x9be1  brtrue.s loc_9BE5
0x9be3  ldnull
0x9be4  ret
0x9be5  ldarg.0
0x9be6  ldc.i4.4
0x9be7  newarr   [mscorlib]System.Object
0x9bec  dup
0x9bed  ldc.i4.0
0x9bee  ldstr    aPortalupload// "PortalUpload_"
0x9bf3  stelem.ref
0x9bf4  dup
0x9bf5  ldc.i4.1
0x9bf6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x9bfb  box      [mscorlib]System.Guid
0x9c00  stelem.ref
0x9c01  dup
0x9c02  ldc.i4.2
0x9c03  ldstr    asc_12500// "_"
0x9c08  stelem.ref
0x9c09  dup
0x9c0a  ldc.i4.3
0x9c0b  ldarg.0
0x9c0c  call     instance class [System]System.Collections.Specialized.NameValueCollection [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::get_FormData()
0x9c11  ldstr    aName// "Name"
0x9c16  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c1b  stelem.ref
0x9c1c  call     string [mscorlib]System.String::Concat(object[])
0x9c21  stfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::_localFileName
0x9c26  ldarg.2
0x9c27  callvirt instance class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentDisposition()
0x9c2c  ldarg.2
0x9c2d  callvirt instance class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentDisposition()
0x9c32  callvirt instance string [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::get_FileName()
0x9c37  dup
0x9c38  brtrue.s loc_9C41
0x9c3a  pop
0x9c3b  ldarg.0
0x9c3c  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::_localFileName
0x9c41  callvirt instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::set_FileName(string)
0x9c46  ldarg.0
0x9c47  ldarg.1
0x9c48  ldarg.2
0x9c49  call     instance class [mscorlib]System.IO.Stream [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::GetStream(class [System.Net.Http]System.Net.Http.HttpContent, class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders)
0x9c4e  ret
0x9c4f  ldarg.0
0x9c50  call     instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetStream()
0x9c55  ret
0x9c56  ldnull
0x9c57  ret
```
