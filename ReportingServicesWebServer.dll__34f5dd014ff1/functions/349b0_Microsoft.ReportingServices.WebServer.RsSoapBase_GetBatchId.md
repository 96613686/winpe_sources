# Microsoft.ReportingServices.WebServer.RsSoapBase::GetBatchId

- ea: `0x349b0`
- end: `0x349f9`
- name: `Microsoft.ReportingServices.WebServer.RsSoapBase::GetBatchId`
- size: `73`
- prototype: ``
- caller_count: `51`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e990`
- `0x2e9b0`
- `0x2ea00`
- `0x2ea20`
- `0x2eaa0`
- `0x2eae0`
- `0x2eb00`
- `0x2eb30`
- `0x2eb50`
- `0x2eb70`
- `0x2ebc0`
- `0x2ebe0`
- `0x2ec10`
- `0x2ec50`
- `0x2ec80`
- `0x2ecb0`
- `0x2ecf0`
- `0x2ed40`
- `0x2ed70`
- `0x2ed90`
- `0x2edb0`
- `0x2edd0`
- `0x2ee10`
- `0x2ee50`
- `0x2ee90`
- `0x2eee0`
- `0x2ef30`
- `0x2ef50`
- `0x2ef70`
- `0x2efd0`
- `0x2eff0`
- `0x2f010`
- `0x2f040`
- `0x2f070`
- `0x2f090`
- `0x2f100`
- `0x2f1c0`
- `0x2f200`
- `0x2f220`
- `0x2f250`
- `0x2f280`
- `0x2f2b0`
- `0x2f2d0`
- `0x2f330`
- `0x2f360`
- `0x2f3f0`
- `0x2f410`
- `0x2f430`
- `0x2f450`
- `0x2f480`

## callees

- `0x33460`
- `0x34930`
- `0x349b0`

## pseudocode

```c

```

## disassembly

```asm
0x349b0  ldarg.0
0x349b1  call     instance class Microsoft.ReportingServices.WebServer.BatchHeader Microsoft.ReportingServices.WebServer.RsSoapBase::get_BatchHeaderValue()
0x349b6  brfalse.s loc_349E2
0x349b8  ldarg.0
0x349b9  call     instance class Microsoft.ReportingServices.WebServer.BatchHeader Microsoft.ReportingServices.WebServer.RsSoapBase::get_BatchHeaderValue()
0x349be  ldfld    string Microsoft.ReportingServices.WebServer.BatchHeader::BatchID
0x349c3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x349c8  stloc.0
0x349c9  leave.s  loc_349F7
0x349cb  pop
0x349cc  ldarg.0
0x349cd  call     instance class Microsoft.ReportingServices.WebServer.BatchHeader Microsoft.ReportingServices.WebServer.RsSoapBase::get_BatchHeaderValue()
0x349d2  ldfld    string Microsoft.ReportingServices.WebServer.BatchHeader::BatchID
0x349d7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.BatchNotFoundException::.ctor(string)
0x349dc  call     class [mscorlib]System.Exception Microsoft.ReportingServices.WebServer.WebServiceHelper::GetSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException exception)
0x349e1  throw
0x349e2  ldarg.1
0x349e3  brfalse.s loc_349F1
0x349e5  ldnull
0x349e6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.BatchNotFoundException::.ctor(string)
0x349eb  call     class [mscorlib]System.Exception Microsoft.ReportingServices.WebServer.WebServiceHelper::GetSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException exception)
0x349f0  throw
0x349f1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x349f6  ret
0x349f7  ldloc.0
0x349f8  ret
```
