# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.CastSegmentHandler::.ctor

- ea: `0xb230`
- end: `0xb246`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.CastSegmentHandler::.ctor`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xbd10`

## callees

- `0xb250`

## pseudocode

```c

```

## disassembly

```asm
0xb230  ldarg.0
0xb231  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem
0xb236  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb23b  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xb240  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.CastSegmentHandler::.ctor(class [mscorlib]System.Reflection.Assembly assembly)
0xb245  ret
```
