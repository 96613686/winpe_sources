# Microsoft.ReportingServices.Modeling.CompilationContext::.ctor_3

- ea: `0x8480`
- end: `0x84d4`
- name: `Microsoft.ReportingServices.Modeling.CompilationContext::.ctor_3`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x171b0`
- `0x23a50`

## callees

- `0x8350`
- `0x8480`
- `0x8530`
- `0x8540`
- `0x8570`
- `0x8580`
- `0x97d0`

## string_xrefs

- `0x84b1`: `persist is false but Normalize/ReplaceParameterRefs/ResolveStaticFunctions is specified.`
- `0x84c8`: `includeSecurityFilter can not be null for query compilation.`

## pseudocode

```c

```

## disassembly

```asm
0x8480  ldarg.0
0x8481  ldarg.1
0x8482  ldc.i4.1
0x8483  ldarg.3
0x8484  ldarg.s  4
0x8486  ldarg.s  5
0x8488  ldarg.s  6
0x848a  call     instance void Microsoft.ReportingServices.Modeling.CompilationContext::.ctor(bool persist, bool checkInvalidRefs, string userID, string userCulture, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> now, class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> includeSecurityFilter)
0x848f  ldarg.0
0x8490  ldarg.2
0x8491  stfld    valuetype Microsoft.ReportingServices.Modeling.QueryCompilationOptions Microsoft.ReportingServices.Modeling.CompilationContext::m_queryOptions
0x8496  ldarg.0
0x8497  call     instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x849c  brtrue.s loc_84AE
0x849e  ldarg.0
0x849f  call     instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldReplaceParameterRefs()
0x84a4  brtrue.s loc_84AE
0x84a6  ldarg.0
0x84a7  call     instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldResolveStaticFunctions()
0x84ac  brfalse.s loc_84BC
0x84ae  ldarg.1
0x84af  brtrue.s loc_84BC
0x84b1  ldstr    aPersistIsFalse// "persist is false but Normalize/ReplaceP"...
0x84b6  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x84bb  throw
0x84bc  ldarg.s  6
0x84be  brtrue.s loc_84D3
0x84c0  ldarg.0
0x84c1  call     instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldApplySecurityFilters()
0x84c6  brfalse.s loc_84D3
0x84c8  ldstr    aIncludesecurit// "includeSecurityFilter can not be null f"...
0x84cd  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x84d2  throw
0x84d3  ret
```
