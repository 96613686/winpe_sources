# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::.cctor

- ea: `0xb80`
- end: `0xbc7`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::.cctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f60`
- `0x1f90`
- `0x1fc0`
- `0x1ff0`
- `0x2020`
- `0x2050`
- `0x2080`

## pseudocode

```c

```

## disassembly

```asm
0xb80  newobj   instance void ChartComponentType::.ctor()
0xb85  stsfld   class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::m_chart
0xb8a  newobj   instance void GaugePanelComponentType::.ctor()
0xb8f  stsfld   class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::m_gaugePanel
0xb94  newobj   instance void ImageComponentType::.ctor()
0xb99  stsfld   class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::m_image
0xb9e  newobj   instance void RectangleComponentType::.ctor()
0xba3  stsfld   class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::m_rectangle
0xba8  newobj   instance void TablixComponentType::.ctor()
0xbad  stsfld   class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::m_tablix
0xbb2  newobj   instance void MapComponentType::.ctor()
0xbb7  stsfld   class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::m_map
0xbbc  newobj   instance void ReportParameterComponentType::.ctor()
0xbc1  stsfld   class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::m_reportParameter
0xbc6  ret
```
