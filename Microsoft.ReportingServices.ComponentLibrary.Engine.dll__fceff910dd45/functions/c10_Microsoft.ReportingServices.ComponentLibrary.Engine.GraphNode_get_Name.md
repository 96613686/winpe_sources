# Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Name

- ea: `0xc10`
- end: `0xc34`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Name`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x15f0`
- `0x1a60`

## callees

- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0xc10  ldarg.0
0xc11  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::m_dependency
0xc16  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.INamedObject
0xc1b  brtrue.s loc_C23
0xc1d  ldsfld   string [mscorlib]System.String::Empty
0xc22  ret
0xc23  ldarg.0
0xc24  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::m_dependency
0xc29  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.INamedObject
0xc2e  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.INamedObject::get_Name()
0xc33  ret
```
