# Microsoft.ReportingServices.Library.SqlAgentScheduler::get_CategoryID

- ea: `0x61a0`
- end: `0x61d8`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::get_CategoryID`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x63e0`

## callees

- `0x61a0`
- `0x61e0`
- `0x6240`

## pseudocode

```c

```

## disassembly

```asm
0x61a0  ldarg.0
0x61a1  stloc.0
0x61a2  ldc.i4.0
0x61a3  stloc.1
0x61a4  ldloc.0
0x61a5  ldloca.s 1
0x61a7  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x61ac  ldsfld   int32 Microsoft.ReportingServices.Library.SqlAgentScheduler::m_categoryId
0x61b1  brtrue.s loc_61B9
0x61b3  ldarg.0
0x61b4  call     instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::GetCategoryIDFromMSDB()
0x61b9  ldsfld   int32 Microsoft.ReportingServices.Library.SqlAgentScheduler::m_categoryId
0x61be  brtrue.s loc_61C6
0x61c0  ldarg.0
0x61c1  call     instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::CreateCategoryID()
0x61c6  leave.s  loc_61D2
0x61c8  ldloc.1
0x61c9  brfalse.s loc_61D1
0x61cb  ldloc.0
0x61cc  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x61d1  endfinally
0x61d2  ldsfld   int32 Microsoft.ReportingServices.Library.SqlAgentScheduler::m_categoryId
0x61d7  ret
```
