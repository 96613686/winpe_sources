# Microsoft.ReportingServices.WebServer.ReportingService2006::Initialize

- ea: `0x2f520`
- end: `0x2f546`
- name: `Microsoft.ReportingServices.WebServer.ReportingService2006::Initialize`
- size: `38`
- prototype: ``
- caller_count: `89`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f550`
- `0x2f570`
- `0x2f590`
- `0x2f5b0`
- `0x2f5d0`
- `0x2f5f0`
- `0x2f610`
- `0x2f630`
- `0x2f650`
- `0x2f670`
- `0x2f690`
- `0x2f6b0`
- `0x2f6d0`
- `0x2f700`
- `0x2f720`
- `0x2f740`
- `0x2f770`
- `0x2f790`
- `0x2f7b0`
- `0x2f7e0`
- `0x2f800`
- `0x2f820`
- `0x2f840`
- `0x2f860`
- `0x2f880`
- `0x2f8a0`
- `0x2f8c0`
- `0x2f8e0`
- `0x2f900`
- `0x2f930`
- `0x2f950`
- `0x2f970`
- `0x2f990`
- `0x2f9b0`
- `0x2f9d0`
- `0x2f9f0`
- `0x2fa10`
- `0x2fa30`
- `0x2fa50`
- `0x2fa70`
- `0x2fa90`
- `0x2fab0`
- `0x2fad0`
- `0x2faf0`
- `0x2fb10`
- `0x2fb30`
- `0x2fb50`
- `0x2fb70`
- `0x2fb90`
- `0x2fbb0`

## callees

- `0x34890`
- `0x348f0`

## pseudocode

```c

```

## disassembly

```asm
0x2f520  ldarg.0
0x2f521  ldarg.1
0x2f522  ldc.i4.1
0x2f523  call     instance void Microsoft.ReportingServices.WebServer.RsSoapBase::Init(string itemPath, bool checkAccessToSharePoint)
0x2f528  ldarg.0
0x2f529  ldarg.0
0x2f52a  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.RsSoapBase::get_Service()
0x2f52f  ldnull
0x2f530  ldftn    class [mscorlib]System.Exception Microsoft.ReportingServices.WebServer.WebServiceHelper::GetSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException exception)
0x2f536  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetExceptionForEndpoint::.ctor(object, native int)
0x2f53b  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportingServiceSPImpl::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetExceptionForEndpoint)
0x2f540  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportingServiceSPImpl Microsoft.ReportingServices.WebServer.ReportingService2006::m_impl
0x2f545  ret
```
