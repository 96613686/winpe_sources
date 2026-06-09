# Microsoft.BIServer.Management.WebApi.WebApiActivator::Create

- ea: `0x1b0`
- end: `0x1fa`
- name: `Microsoft.BIServer.Management.WebApi.WebApiActivator::Create`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1b0`
- `0x900`
- `0x930`
- `0xa50`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldarg.3
0x1b1  ldtoken  Microsoft.BIServer.Management.WebApi.Controllers.KeysController
0x1b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c0  brfalse.s loc_1C8
0x1c2  newobj   instance void Microsoft.BIServer.Management.WebApi.Controllers.KeysController::.ctor()
0x1c7  ret
0x1c8  ldarg.3
0x1c9  ldtoken  Microsoft.BIServer.Management.WebApi.Controllers.ConfigController
0x1ce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1d8  brfalse.s loc_1E0
0x1da  newobj   instance void Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::.ctor()
0x1df  ret
0x1e0  ldarg.3
0x1e1  ldtoken  Microsoft.BIServer.Management.WebApi.Controllers.StateController
0x1e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1eb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1f0  brfalse.s loc_1F8
0x1f2  newobj   instance void Microsoft.BIServer.Management.WebApi.Controllers.StateController::.ctor()
0x1f7  ret
0x1f8  ldnull
0x1f9  ret
```
