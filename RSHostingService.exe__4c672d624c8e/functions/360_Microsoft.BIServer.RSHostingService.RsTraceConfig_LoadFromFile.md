# Microsoft.BIServer.RSHostingService.RsTraceConfig::LoadFromFile

- ea: `0x360`
- end: `0x370`
- name: `Microsoft.BIServer.RSHostingService.RsTraceConfig::LoadFromFile`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1030`
- `0x12b0`
- `0x2430`

## callees

- `0x370`

## string_xrefs

- `0x360`: `..\ReportServer\bin\ReportingServicesService.exe.config`

## pseudocode

```c

```

## disassembly

```asm
0x360  ldstr    aReportserverBi// "..\\ReportServer\\bin\\ReportingService"...
0x365  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x36a  newobj   instance void Microsoft.BIServer.RSHostingService.RsTraceConfig::.ctor(string contents)
0x36f  ret
```
