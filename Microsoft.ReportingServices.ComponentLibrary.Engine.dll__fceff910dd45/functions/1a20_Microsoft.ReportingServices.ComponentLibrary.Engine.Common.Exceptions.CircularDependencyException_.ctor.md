# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.CircularDependencyException::.ctor

- ea: `0x1a20`
- end: `0x1a42`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.CircularDependencyException::.ctor`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1580`

## callees

- `0x19a0`
- `0x1a20`
- `0x1a60`

## string_xrefs

- `0x1a2f`: `circularPath`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarg.0
0x1a21  ldarg.1
0x1a22  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.CircularDependencyException::BuildErrorString(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> circularPath)
0x1a27  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.ComponentEngineException::.ctor(string message)
0x1a2c  ldarg.1
0x1a2d  brtrue.s loc_1A3A
0x1a2f  ldstr    aCircularpath// "circularPath"
0x1a34  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a39  throw
0x1a3a  ldarg.0
0x1a3b  ldarg.1
0x1a3c  stfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.CircularDependencyException::m_circularPath
0x1a41  ret
```
