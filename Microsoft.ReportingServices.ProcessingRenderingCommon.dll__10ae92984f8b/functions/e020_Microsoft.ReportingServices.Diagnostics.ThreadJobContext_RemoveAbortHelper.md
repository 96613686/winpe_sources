# Microsoft.ReportingServices.Diagnostics.ThreadJobContext::RemoveAbortHelper

- ea: `0xe020`
- end: `0xe061`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadJobContext::RemoveAbortHelper`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0xe020`

## string_xrefs

- `0xe042`: `No abort helper to remove`

## pseudocode

```c

```

## disassembly

```asm
0xe020  ldarg.0
0xe021  ldfld    bool Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_disposed
0xe026  brfalse.s loc_E029
0xe028  ret
0xe029  ldarg.0
0xe02a  ldfld    object Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_abortHelperSync
0xe02f  stloc.0
0xe030  ldc.i4.0
0xe031  stloc.1
0xe032  ldloc.0
0xe033  ldloca.s 1
0xe035  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xe03a  ldarg.0
0xe03b  ldfld    class Microsoft.ReportingServices.Diagnostics.IAbortHelper Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_abortHelper
0xe040  brtrue.s loc_E04D
0xe042  ldstr    aNoAbortHelperT// "No abort helper to remove"
0xe047  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xe04c  throw
0xe04d  ldarg.0
0xe04e  ldnull
0xe04f  stfld    class Microsoft.ReportingServices.Diagnostics.IAbortHelper Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_abortHelper
0xe054  leave.s  loc_E060
0xe056  ldloc.1
0xe057  brfalse.s loc_E05F
0xe059  ldloc.0
0xe05a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xe05f  endfinally
0xe060  ret
```
