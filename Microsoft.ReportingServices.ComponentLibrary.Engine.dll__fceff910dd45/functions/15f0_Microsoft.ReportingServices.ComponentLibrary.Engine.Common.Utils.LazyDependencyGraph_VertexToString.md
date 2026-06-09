# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::VertexToString

- ea: `0x15f0`
- end: `0x1630`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::VertexToString`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xc10`
- `0xc40`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldarg.1
0x15f1  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x15f6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x15fb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1600  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x1605  dup
0x1606  ldstr    asc_3594// "["
0x160b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1610  pop
0x1611  dup
0x1612  ldarg.1
0x1613  callvirt instance string Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Name()
0x1618  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x161d  pop
0x161e  dup
0x161f  ldstr    asc_3598// "]"
0x1624  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1629  pop
0x162a  callvirt instance string [mscorlib]System.Object::ToString()
0x162f  ret
```
