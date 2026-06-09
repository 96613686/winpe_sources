# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::.ctor

- ea: `0x7a0`
- end: `0x7f3`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::.ctor`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x7a0`
- `0x860`
- `0xd20`
- `0x19b0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldarg.0
0x7a1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject, class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem>::.ctor()
0x7a6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject, class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem> Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_components
0x7ab  ldarg.0
0x7ac  call     instance void [mscorlib]System.Object::.ctor()
0x7b1  ldarg.1
0x7b2  brtrue.s loc_7BF
0x7b4  ldstr    aStream// "stream"
0x7b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7be  throw
0x7bf  nop
0x7c0  ldarg.1
0x7c1  ldc.i4.0
0x7c2  conv.i8
0x7c3  ldc.i4.0
0x7c4  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x7c9  pop
0x7ca  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer::.ctor()
0x7cf  stloc.0
0x7d0  ldarg.0
0x7d1  ldloc.0
0x7d2  ldarg.1
0x7d3  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer::Deserialize(class [mscorlib]System.IO.Stream)
0x7d8  stfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_report
0x7dd  leave.s  loc_7EC
0x7df  stloc.1
0x7e0  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ReportDocument_DeserializationFailed()
0x7e5  ldloc.1
0x7e6  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.ComponentEngineException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x7eb  throw
0x7ec  ldarg.0
0x7ed  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::ShredDocument()
0x7f2  ret
```
