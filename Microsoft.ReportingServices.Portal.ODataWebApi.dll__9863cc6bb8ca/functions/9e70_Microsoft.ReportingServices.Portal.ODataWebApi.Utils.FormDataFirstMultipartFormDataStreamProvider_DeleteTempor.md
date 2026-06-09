# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::DeleteTemporaryFile

- ea: `0x9e70`
- end: `0x9e91`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::DeleteTemporaryFile`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x9e50`
- `0x9e70`
- `0x9ea0`

## pseudocode

```c

```

## disassembly

```asm
0x9e70  ldarg.0
0x9e71  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetTempFilename()
0x9e76  stloc.0
0x9e77  ldloc.0
0x9e78  call     bool [mscorlib]System.IO.File::Exists(string)
0x9e7d  brfalse.s loc_9E85
0x9e7f  ldloc.0
0x9e80  call     void [mscorlib]System.IO.File::Delete(string)
0x9e85  ldarg.0
0x9e86  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::DeleteOldUploadedFiles()
0x9e8b  leave.s  loc_9E90
0x9e8d  pop
0x9e8e  leave.s  loc_9E90
0x9e90  ret
```
