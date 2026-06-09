# Microsoft.ReportingServices.OnDemandReportRendering.InteractivityPaginationModuleFactory::CreateInteractivityPaginationModule

- ea: `0x1cfe0`
- end: `0x1cffa`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.InteractivityPaginationModuleFactory::CreateInteractivityPaginationModule`
- size: `26`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x177380`
- `0x177410`
- `0x177490`
- `0x177530`
- `0x1775b0`
- `0x177660`
- `0x177810`
- `0x1779e0`
- `0x177c20`

## string_xrefs

- `0x1cfe0`: `Microsoft.ReportingServices.SPBProcessing`
- `0x1cfe5`: `Microsoft.ReportingServices.Rendering.SPBProcessing.SPBInteractivityProcessing`

## pseudocode

```c

```

## disassembly

```asm
0x1cfe0  ldstr    aMicrosoftRepor_1// "Microsoft.ReportingServices.SPBProcessi"...
0x1cfe5  ldstr    aMicrosoftRepor_2// "Microsoft.ReportingServices.Rendering.S"...
0x1cfea  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x1cfef  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x1cff4  castclass Microsoft.ReportingServices.OnDemandReportRendering.IInteractivityPaginationModule
0x1cff9  ret
```
