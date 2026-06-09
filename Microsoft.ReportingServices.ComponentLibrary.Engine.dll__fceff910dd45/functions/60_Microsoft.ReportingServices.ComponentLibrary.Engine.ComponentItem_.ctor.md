# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::.ctor

- ea: `0x60`
- end: `0x7d`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::.ctor`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3d0`
- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x60  ldarg.0
0x61  newobj   instance void ComponentProperties::.ctor()
0x66  stfld    class ComponentProperties Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_componentProperies
0x6b  ldarg.0
0x6c  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::.ctor()
0x71  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_rdlFragment
0x76  ldarg.0
0x77  call     instance void [mscorlib]System.Object::.ctor()
0x7c  ret
```
