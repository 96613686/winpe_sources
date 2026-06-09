# <>c__DisplayClass1_1::<Create>b__0

- ea: `0x1ed0`
- end: `0x1ef0`
- name: `<>c__DisplayClass1_1::<Create>b__0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0xc40`
- `0x1ed0`

## pseudocode

```c

```

## disassembly

```asm
0x1ed0  ldarg.1
0x1ed1  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x1ed6  ldarg.0
0x1ed7  ldfld    class <>c__DisplayClass1_0 <>c__DisplayClass1_1::CS$<>8__locals1
0x1edc  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject <>c__DisplayClass1_0::rdlObject
0x1ee1  beq.s    loc_1EEF
0x1ee3  ldarg.0
0x1ee4  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> <>c__DisplayClass1_1::subgraphNodes
0x1ee9  ldarg.1
0x1eea  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::Add(var<u1>)
0x1eef  ret
```
