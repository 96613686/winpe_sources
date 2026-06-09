# Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::CreateStateManager

- ea: `0x1faf40`
- end: `0x1faf84`
- name: `Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::CreateStateManager`
- size: `68`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1fa620`
- `0x1fa830`
- `0x1fad60`

## callees

- `0x1faf40`
- `0x1fd680`
- `0x1fe520`
- `0x1fe750`

## string_xrefs

- `0x1faf6f`: `CreateStateManager: invalid contextMode.`
- `0x1faf79`: `CreateStateManager: invalid contextMode.`

## pseudocode

```c

```

## disassembly

```asm
0x1faf40  ldarg.1
0x1faf41  switch   loc_1FAF5B, loc_1FAF54, loc_1FAF62
0x1faf52  br.s     loc_1FAF69
0x1faf54  ldarg.0
0x1faf55  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerStreaming::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x1faf5a  ret
0x1faf5b  ldarg.0
0x1faf5c  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x1faf61  ret
0x1faf62  ldarg.0
0x1faf63  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerDefinitionOnly::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x1faf68  ret
0x1faf69  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1faf6e  ldc.i4.0
0x1faf6f  ldstr    aCreatestateman// "CreateStateManager: invalid contextMode"...
0x1faf74  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1faf79  ldstr    aCreatestateman// "CreateStateManager: invalid contextMode"...
0x1faf7e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1faf83  throw
```
