# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::SaveNameToResult

- ea: `0x9c90`
- end: `0x9cc1`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::SaveNameToResult`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b70`

## callees

- `0x9c90`

## pseudocode

```c

```

## disassembly

```asm
0x9c90  ldarg.0
0x9c91  ldarg.1
0x9c92  callvirt instance class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentDisposition()
0x9c97  callvirt instance string [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::get_Name()
0x9c9c  brtrue.s loc_9CA1
0x9c9e  ldnull
0x9c9f  br.s     loc_9CBB
0x9ca1  ldarg.1
0x9ca2  callvirt instance class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentDisposition()
0x9ca7  callvirt instance string [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::get_Name()
0x9cac  ldstr    asc_12504// "\""
0x9cb1  ldstr    asc_12508// ""
0x9cb6  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x9cbb  stfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::_lastFormKey
0x9cc0  ret
```
