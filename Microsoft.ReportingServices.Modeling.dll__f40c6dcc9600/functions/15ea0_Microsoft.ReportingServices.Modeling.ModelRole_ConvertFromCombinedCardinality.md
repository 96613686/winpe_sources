# Microsoft.ReportingServices.Modeling.ModelRole::ConvertFromCombinedCardinality

- ea: `0x15ea0`
- end: `0x15ef1`
- name: `Microsoft.ReportingServices.Modeling.ModelRole::ConvertFromCombinedCardinality`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x15620`

## callees

- `0x97d0`
- `0x15ea0`

## string_xrefs

- `0x15ed4`: `Unknown CombinedCardinality value: `

## pseudocode

```c

```

## disassembly

```asm
0x15ea0  ldarg.0
0x15ea1  switch   loc_15EB8, loc_15EBF, loc_15EC6, loc_15ECD
0x15eb6  br.s     loc_15ED4
0x15eb8  ldarg.1
0x15eb9  ldc.i4.0
0x15eba  stind.i1
0x15ebb  ldarg.2
0x15ebc  ldc.i4.1
0x15ebd  stind.i1
0x15ebe  ret
0x15ebf  ldarg.1
0x15ec0  ldc.i4.1
0x15ec1  stind.i1
0x15ec2  ldarg.2
0x15ec3  ldc.i4.1
0x15ec4  stind.i1
0x15ec5  ret
0x15ec6  ldarg.1
0x15ec7  ldc.i4.0
0x15ec8  stind.i1
0x15ec9  ldarg.2
0x15eca  ldc.i4.0
0x15ecb  stind.i1
0x15ecc  ret
0x15ecd  ldarg.1
0x15ece  ldc.i4.1
0x15ecf  stind.i1
0x15ed0  ldarg.2
0x15ed1  ldc.i4.0
0x15ed2  stind.i1
0x15ed3  ret
0x15ed4  ldstr    aUnknownCombine// "Unknown CombinedCardinality value: "
0x15ed9  ldarga.s 0
0x15edb  constrained. Microsoft.ReportingServices.Modeling.CombinedCardinality
0x15ee1  callvirt instance string [mscorlib]System.Object::ToString()
0x15ee6  call     string [mscorlib]System.String::Concat(string, string)
0x15eeb  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x15ef0  throw
```
