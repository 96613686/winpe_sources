# Microsoft.ReportingServices.OnDemandReportRendering.DataSegmentRendererFactory::CreateDataSegmentRenderer

- ea: `0x1ce80`
- end: `0x1ce9a`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.DataSegmentRendererFactory::CreateDataSegmentRenderer`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f09e0`

## string_xrefs

- `0x1ce80`: `Microsoft.ReportingServices.DataSegmentRendering`
- `0x1ce85`: `Microsoft.ReportingServices.Rendering.DataSegmentRenderer.DataSegmentRenderer`

## pseudocode

```c

```

## disassembly

```asm
0x1ce80  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.DataSegment"...
0x1ce85  ldstr    aMicrosoftRepor_0// "Microsoft.ReportingServices.Rendering.D"...
0x1ce8a  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x1ce8f  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x1ce94  castclass Microsoft.ReportingServices.OnDemandReportRendering.IDataSegmentRenderer
0x1ce99  ret
```
