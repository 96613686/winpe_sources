# Microsoft.ReportingServices.Modeling.CompilationContext::set_ParameterValues

- ea: `0x85b0`
- end: `0x85ce`
- name: `Microsoft.ReportingServices.Modeling.CompilationContext::set_ParameterValues`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x23a50`
- `0x23f50`

## callees

- `0x85b0`
- `0x97d0`

## string_xrefs

- `0x85bb`: `Compilation with parameters but not persist is not supported`

## pseudocode

```c

```

## disassembly

```asm
0x85b0  ldarg.1
0x85b1  brfalse.s loc_85C6
0x85b3  ldarg.0
0x85b4  ldfld    bool Microsoft.ReportingServices.Modeling.CompilationContext::m_persist
0x85b9  brtrue.s loc_85C6
0x85bb  ldstr    aCompilationWit// "Compilation with parameters but not per"...
0x85c0  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x85c5  throw
0x85c6  ldarg.0
0x85c7  ldarg.1
0x85c8  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Modeling.CompilationContext::m_parameterValues
0x85cd  ret
```
