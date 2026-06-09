# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType_1

- ea: `0xb30`
- end: `0xb4a`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType_1`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x690`

## callees

- `0xad0`
- `0xb30`

## pseudocode

```c

```

## disassembly

```asm
0xb30  ldarg.0
0xb31  brtrue.s loc_B3E
0xb33  ldstr    aRdlobject// "rdlObject"
0xb38  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb3d  throw
0xb3e  ldarg.0
0xb3f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb44  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType(class [mscorlib]System.Type rdlType)
0xb49  ret
```
