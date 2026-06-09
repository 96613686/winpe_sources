# Microsoft.ReportingServices.Modeling.ResultType::SetEntityKeyTarget

- ea: `0x19d40`
- end: `0x19d86`
- name: `Microsoft.ReportingServices.Modeling.ResultType::SetEntityKeyTarget`
- size: `70`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18a90`
- `0x1a9a0`
- `0x368b0`
- `0x369f0`

## callees

- `0x97d0`
- `0x19d40`

## string_xrefs

- `0x19d7b`: `Attempt to reassign m_entityKeyTarget.`

## pseudocode

```c

```

## disassembly

```asm
0x19d40  ldarg.1
0x19d41  brtrue.s loc_19D4E
0x19d43  ldstr    aEntitykeytarge// "entityKeyTarget is null"
0x19d48  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x19d4d  throw
0x19d4e  ldarg.0
0x19d4f  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::m_dataType
0x19d54  ldc.i4.7
0x19d55  beq.s    loc_19D6B
0x19d57  ldarg.0
0x19d58  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::m_dataType
0x19d5d  ldc.i4.8
0x19d5e  beq.s    loc_19D6B
0x19d60  ldstr    aSetentitykeyta_0// "SetEntityKeyTarget is called on a non-e"...
0x19d65  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x19d6a  throw
0x19d6b  ldarg.0
0x19d6c  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.ResultType::m_entityKeyTarget
0x19d71  brtrue.s loc_19D7B
0x19d73  ldarg.0
0x19d74  ldarg.1
0x19d75  stfld    class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.ResultType::m_entityKeyTarget
0x19d7a  ret
0x19d7b  ldstr    aAttemptToReass// "Attempt to reassign m_entityKeyTarget."
0x19d80  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x19d85  throw
```
