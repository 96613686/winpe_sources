# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetTempFilename

- ea: `0x9e50`
- end: `0x9e63`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetTempFilename`
- size: `19`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9e70`
- `0x9f20`
- `0x9f30`

## pseudocode

```c

```

## disassembly

```asm
0x9e50  ldarg.0
0x9e51  call     instance string [System.Net.Http.Formatting]System.Net.Http.MultipartFileStreamProvider::get_RootPath()
0x9e56  ldarg.0
0x9e57  ldnull
0x9e58  callvirt instance string [System.Net.Http.Formatting]System.Net.Http.MultipartFileStreamProvider::GetLocalFileName(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders)
0x9e5d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x9e62  ret
```
