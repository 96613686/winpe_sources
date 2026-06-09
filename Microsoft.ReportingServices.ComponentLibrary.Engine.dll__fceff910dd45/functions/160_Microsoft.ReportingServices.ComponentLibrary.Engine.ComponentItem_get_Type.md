# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Type

- ea: `0x160`
- end: `0x19a`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Type`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c0`
- `0x340`

## callees

- `0x160`
- `0x1f0`
- `0xa70`
- `0xcc0`
- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldnull
0x161  stloc.0
0x162  ldarg.0
0x163  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x168  ldstr    aType_0// "Type"
0x16d  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x172  brfalse.s loc_18A
0x174  ldarg.0
0x175  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x17a  ldstr    aType_0// "Type"
0x17f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x184  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType(string rdlTypeName)
0x189  stloc.0
0x18a  ldloc.0
0x18b  brtrue.s loc_198
0x18d  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidType()
0x192  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.ComponentEngineException::.ctor(string message)
0x197  throw
0x198  ldloc.0
0x199  ret
```
