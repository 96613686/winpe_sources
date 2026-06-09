# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::.ctor_0

- ea: `0x800`
- end: `0x82d`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::.ctor_0`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e0`

## callees

- `0x800`
- `0x860`

## pseudocode

```c

```

## disassembly

```asm
0x800  ldarg.0
0x801  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject, class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem>::.ctor()
0x806  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject, class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem> Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_components
0x80b  ldarg.0
0x80c  call     instance void [mscorlib]System.Object::.ctor()
0x811  ldarg.1
0x812  brtrue.s loc_81F
0x814  ldstr    aReport// "report"
0x819  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x81e  throw
0x81f  ldarg.0
0x820  ldarg.1
0x821  stfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_report
0x826  ldarg.0
0x827  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::ShredDocument()
0x82c  ret
```
