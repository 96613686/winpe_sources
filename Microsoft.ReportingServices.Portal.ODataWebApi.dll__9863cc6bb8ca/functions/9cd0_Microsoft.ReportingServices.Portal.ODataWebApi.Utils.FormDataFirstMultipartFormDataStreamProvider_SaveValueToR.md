# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::SaveValueToResult

- ea: `0x9cd0`
- end: `0x9d0f`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::SaveValueToResult`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b70`

## callees

- `0x9cd0`

## pseudocode

```c

```

## disassembly

```asm
0x9cd0  ldarg.0
0x9cd1  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::_lastFormKey
0x9cd6  brfalse.s loc_9D0E
0x9cd8  ldarg.0
0x9cd9  ldfld    class [mscorlib]System.IO.MemoryStream Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::_formValueMemoryStream
0x9cde  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x9ce3  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x9ce8  stloc.0
0x9ce9  ldloc.0
0x9cea  call     string [System.Web]System.Web.HttpUtility::HtmlDecode(string)
0x9cef  stloc.0
0x9cf0  ldloc.0
0x9cf1  ldstr    asc_12504// "\""
0x9cf6  ldstr    asc_12508// ""
0x9cfb  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x9d00  stloc.0
0x9d01  ldarg.1
0x9d02  ldarg.0
0x9d03  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::_lastFormKey
0x9d08  ldloc.0
0x9d09  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x9d0e  ret
```
