# Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::.ctor

- ea: `0xbe0`
- end: `0xc03`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::.ctor`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x910`
- `0x950`
- `0x990`
- `0x1630`

## callees

- `0xbe0`

## pseudocode

```c

```

## disassembly

```asm
0xbe0  ldarg.0
0xbe1  call     instance void [mscorlib]System.Object::.ctor()
0xbe6  ldarg.1
0xbe7  brtrue.s loc_BF4
0xbe9  ldstr    aDependency// "dependency"
0xbee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbf3  throw
0xbf4  ldarg.0
0xbf5  ldarg.1
0xbf6  stfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::m_dependency
0xbfb  ldarg.0
0xbfc  ldc.i4.0
0xbfd  stfld    bool Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::m_hasCodeDependency
0xc02  ret
```
