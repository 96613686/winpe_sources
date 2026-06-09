# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetSharedDataSetJsonRenderExtension

- ea: `0x6c50`
- end: `0x6c90`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetSharedDataSetJsonRenderExtension`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6bc0`

## callees

- `0x4fb0`
- `0x4fd0`
- `0x4ff0`
- `0x5030`
- `0x5070`
- `0x5090`
- `0x6330`

## string_xrefs

- `0x6c56`: `Microsoft.ReportingServices.DataRendering`
- `0x6c61`: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport`
- `0x6c73`: `SHAREDDATASETJSON`

## pseudocode

```c

```

## disassembly

```asm
0x6c50  newobj   instance void Microsoft.ReportingServices.Diagnostics.RenderingExtension::.ctor()
0x6c55  dup
0x6c56  ldstr    aMicrosoftRepor_1// "Microsoft.ReportingServices.DataRenderi"...
0x6c5b  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Assembly(string value)
0x6c60  dup
0x6c61  ldstr    aMicrosoftRepor_2// "Microsoft.ReportingServices.Rendering.D"...
0x6c66  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Class(string value)
0x6c6b  dup
0x6c6c  ldc.i4.1
0x6c6d  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_LogAllExecutionRequests(bool value)
0x6c72  dup
0x6c73  ldstr    aShareddatasetj// "SHAREDDATASETJSON"
0x6c78  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Name(string value)
0x6c7d  dup
0x6c7e  ldc.i4.0
0x6c7f  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Visible(bool value)
0x6c84  dup
0x6c85  ldstr    aRender// "Render"
0x6c8a  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x6c8f  ret
```
