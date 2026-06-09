# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::GetAsString

- ea: `0x4b0`
- end: `0x4d2`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::GetAsString`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x420`

## callees

- `0x4b0`

## string_xrefs

- `0x4c2`: ` function: scopeName parameter type needs to be string.`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  ldarg.2
0x4b1  brtrue.s loc_4B5
0x4b3  ldnull
0x4b4  ret
0x4b5  ldarg.2
0x4b6  isinst   [mscorlib]System.String
0x4bb  stloc.0
0x4bc  ldloc.0
0x4bd  brfalse.s loc_4C1
0x4bf  ldloc.0
0x4c0  ret
0x4c1  ldarg.1
0x4c2  ldstr    aFunctionScopen// " function: scopeName parameter type nee"...
0x4c7  call     string [mscorlib]System.String::Concat(string, string)
0x4cc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d1  throw
```
