# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.CastSegmentHandler::.ctor_0

- ea: `0xb250`
- end: `0xb272`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.CastSegmentHandler::.ctor_0`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xb230`

## callees

- `0xb250`

## pseudocode

```c

```

## disassembly

```asm
0xb250  ldarg.0
0xb251  call     instance void [mscorlib]System.Object::.ctor()
0xb256  ldarg.1
0xb257  ldnull
0xb258  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0xb25d  brfalse.s loc_B26A
0xb25f  ldstr    aAssembly// "assembly"
0xb264  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb269  throw
0xb26a  ldarg.0
0xb26b  ldarg.1
0xb26c  stfld    class [mscorlib]System.Reflection.Assembly Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.CastSegmentHandler::_assembly
0xb271  ret
```
