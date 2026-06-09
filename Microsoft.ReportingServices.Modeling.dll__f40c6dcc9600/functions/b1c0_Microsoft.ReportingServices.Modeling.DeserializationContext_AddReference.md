# Microsoft.ReportingServices.Modeling.DeserializationContext::AddReference

- ea: `0xb1c0`
- end: `0xb21d`
- name: `Microsoft.ReportingServices.Modeling.DeserializationContext::AddReference`
- size: `93`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xf4b0`
- `0x117f0`
- `0x12620`
- `0x15620`
- `0x1b460`
- `0x1bc00`
- `0x1c100`
- `0x1ef80`
- `0x21dc0`
- `0x22380`
- `0x33de0`
- `0x34e60`
- `0x34f60`
- `0x37bd0`
- `0x37d50`

## callees

- `0x97d0`
- `0xb1c0`
- `0x25c10`
- `0x2ecd0`

## string_xrefs

- `0xb1d6`: `Cannot add reference during CompleteLoad`

## pseudocode

```c

```

## disassembly

```asm
0xb1c0  ldarg.1
0xb1c1  brtrue.s loc_B1CE
0xb1c3  ldstr    aItemIsNull// "item is null"
0xb1c8  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xb1cd  throw
0xb1ce  ldarg.0
0xb1cf  ldfld    bool Microsoft.ReportingServices.Modeling.DeserializationContext::m_completing
0xb1d4  brfalse.s loc_B1E1
0xb1d6  ldstr    aCannotAddRefer// "Cannot add reference during CompleteLoa"...
0xb1db  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xb1e0  throw
0xb1e1  ldarg.0
0xb1e2  ldfld    class StateDictionary Microsoft.ReportingServices.Modeling.DeserializationContext::m_stateContainers
0xb1e7  ldarg.1
0xb1e8  ldloca.s 0
0xb1ea  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.IDeserializationCallback, valuetype StateContainer>::TryGetValue(var<u1>, !!T0)
0xb1ef  brtrue.s loc_B210
0xb1f1  ldloca.s 0
0xb1f3  ldarg.0
0xb1f4  ldfld    class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.DeserializationContext::m_validationCtx
0xb1f9  callvirt instance valuetype State Microsoft.ReportingServices.Modeling.ValidationContext::GetCurrentState()
0xb1fe  call     instance void StateContainer::.ctor(valuetype State validationState)
0xb203  ldarg.0
0xb204  ldfld    class StateDictionary Microsoft.ReportingServices.Modeling.DeserializationContext::m_stateContainers
0xb209  ldarg.1
0xb20a  ldloc.0
0xb20b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.IDeserializationCallback, valuetype StateContainer>::Add(var<u1>, !!T0)
0xb210  ldloc.0
0xb211  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Modeling.ModelingReference> StateContainer::ReferenceList
0xb216  ldarg.2
0xb217  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Modeling.ModelingReference>::Add(var<u1>)
0xb21c  ret
```
