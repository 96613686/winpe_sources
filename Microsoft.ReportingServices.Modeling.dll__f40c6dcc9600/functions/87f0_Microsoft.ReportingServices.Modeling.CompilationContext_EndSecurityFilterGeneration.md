# Microsoft.ReportingServices.Modeling.CompilationContext::EndSecurityFilterGeneration

- ea: `0x87f0`
- end: `0x8823`
- name: `Microsoft.ReportingServices.Modeling.CompilationContext::EndSecurityFilterGeneration`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x10a50`

## callees

- `0x8740`
- `0x87f0`
- `0x97d0`

## string_xrefs

- `0x8804`: `Attempt to restore expression stack when it is not empty.`

## pseudocode

```c

```

## disassembly

```asm
0x87f0  ldarg.0
0x87f1  call     instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x87f6  ldarg.0
0x87f7  ldfld    class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.Expression> Microsoft.ReportingServices.Modeling.CompilationContext::m_expressionStack
0x87fc  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x8801  ldc.i4.0
0x8802  ble.s    loc_880F
0x8804  ldstr    aAttemptToResto// "Attempt to restore expression stack whe"...
0x8809  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x880e  throw
0x880f  ldarg.0
0x8810  ldarg.1
0x8811  stfld    class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.Expression> Microsoft.ReportingServices.Modeling.CompilationContext::m_expressionStack
0x8816  ldarg.0
0x8817  ldfld    class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.IQueryEntity> Microsoft.ReportingServices.Modeling.CompilationContext::m_tryGetSecurityFilterStack
0x881c  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.IQueryEntity>::Pop()
0x8821  pop
0x8822  ret
```
