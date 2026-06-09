# Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_InitialAndOnlyThreadCtx

- ea: `0xd3d0`
- end: `0xd3fb`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_InitialAndOnlyThreadCtx`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a30`

## callees

- `0xd3d0`

## string_xrefs

- `0xd3de`: `Expected only one thread`

## pseudocode

```c

```

## disassembly

```asm
0xd3d0  ldarg.0
0xd3d1  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd3d6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd3db  ldc.i4.1
0xd3dc  beq.s    loc_D3E9
0xd3de  ldstr    aExpectedOnlyOn// "Expected only one thread"
0xd3e3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xd3e8  throw
0xd3e9  ldarg.0
0xd3ea  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd3ef  ldc.i4.0
0xd3f0  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd3f5  castclass Microsoft.ReportingServices.Diagnostics.ThreadJobContext
0xd3fa  ret
```
