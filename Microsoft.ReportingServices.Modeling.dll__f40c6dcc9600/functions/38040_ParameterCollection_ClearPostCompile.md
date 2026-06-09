# ParameterCollection::ClearPostCompile

- ea: `0x38040`
- end: `0x3805f`
- name: `ParameterCollection::ClearPostCompile`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x23da0`

## callees

- `0x97d0`
- `0x38040`

## string_xrefs

- `0x38048`: `ClearPostCompile called on uncompiled collection`

## pseudocode

```c

```

## disassembly

```asm
0x38040  ldarg.0
0x38041  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.Parameter>::get_IsReadOnly()
0x38046  brtrue.s loc_38053
0x38048  ldstr    aClearpostcompi// "ClearPostCompile called on uncompiled c"...
0x3804d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x38052  throw
0x38053  ldarg.0
0x38054  call     instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.Parameter>::get_Items()
0x38059  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.Parameter>::Clear()
0x3805e  ret
```
