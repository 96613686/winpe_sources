# Microsoft.Reporting.WebForms.ServerReport::ConstructServiceObject

- ea: `0x24560`
- end: `0x24582`
- name: `Microsoft.Reporting.WebForms.ServerReport::ConstructServiceObject`
- size: `34`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x23be0`
- `0x23c30`
- `0x23cf0`
- `0x23d30`
- `0x23e50`
- `0x23f20`
- `0x23f40`
- `0x23ff0`
- `0x24020`
- `0x24050`
- `0x24080`
- `0x240b0`
- `0x240f0`
- `0x24140`
- `0x241b0`
- `0x24210`
- `0x24270`
- `0x24590`

## callees

- `0x238d0`
- `0x31280`
- `0x31c50`
- `0x31c60`
- `0x3c840`

## pseudocode

```c

```

## disassembly

```asm
0x24560  newobj   instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::.ctor()
0x24565  dup
0x24566  newobj   instance void ExecutionHeader::.ctor()
0x2456b  callvirt instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::set_ExecutionHeaderValue(class ExecutionHeader value)
0x24570  dup
0x24571  callvirt instance class ExecutionHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_ExecutionHeaderValue()
0x24576  ldarg.0
0x24577  call     instance string Microsoft.Reporting.WebForms.ServerReport::get_ExecutionID()
0x2457c  stfld    string ExecutionHeader::ExecutionID
0x24581  ret
```
