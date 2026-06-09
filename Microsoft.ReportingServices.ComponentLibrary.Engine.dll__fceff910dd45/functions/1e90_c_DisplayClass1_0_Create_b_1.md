# <>c__DisplayClass1_0::<Create>b__1

- ea: `0x1e90`
- end: `0x1ea2`
- name: `<>c__DisplayClass1_0::<Create>b__1`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x380`
- `0xc40`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.0
0x1e91  ldfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem <>c__DisplayClass1_0::component
0x1e96  ldarg.1
0x1e97  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x1e9c  callvirt instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::AddDependency(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject rdlObject)
0x1ea1  ret
```
