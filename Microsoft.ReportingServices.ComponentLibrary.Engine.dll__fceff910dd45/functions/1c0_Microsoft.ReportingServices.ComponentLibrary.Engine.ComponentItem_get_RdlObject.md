# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_RdlObject

- ea: `0x1c0`
- end: `0x1e6`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_RdlObject`
- size: `38`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a0`
- `0x1b0`
- `0x2e0`
- `0x340`

## callees

- `0x110`
- `0x160`
- `0x1c0`
- `0x440`
- `0xcd0`
- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  ldfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_rdlFragment
0x1c6  ldarg.0
0x1c7  call     instance class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Type()
0x1cc  ldarg.0
0x1cd  call     instance string Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Name()
0x1d2  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::GetRdlObject(class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType type, string name)
0x1d7  dup
0x1d8  brtrue.s loc_1E5
0x1da  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidContent()
0x1df  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.ComponentEngineException::.ctor(string message)
0x1e4  throw
0x1e5  ret
```
