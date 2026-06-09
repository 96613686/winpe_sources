# Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::Register

- ea: `0xed60`
- end: `0xedac`
- name: `Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::Register`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xebe0`

## callees

- `0xec90`
- `0xed50`
- `0xed60`
- `0xf210`
- `0xf400`

## pseudocode

```c

```

## disassembly

```asm
0xed60  call     class Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::GetMAPGroup()
0xed65  stloc.0
0xed66  ldarg.0
0xed67  newobj   instance void [mscorlib]System.WeakReference::.ctor(object)
0xed6c  stloc.1
0xed6d  ldarg.0
0xed6e  ldloc.1
0xed6f  callvirt instance void Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::set_CollectionToken(object value)
0xed74  ldloc.0
0xed75  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.WeakReference, class [mscorlib]System.WeakReference> Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_maps
0xed7a  stloc.2
0xed7b  ldc.i4.0
0xed7c  stloc.3
0xed7d  ldloc.2
0xed7e  ldloca.s 3
0xed80  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xed85  ldloc.0
0xed86  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.WeakReference, class [mscorlib]System.WeakReference> Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_maps
0xed8b  ldloc.1
0xed8c  ldloc.1
0xed8d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.WeakReference, class [mscorlib]System.WeakReference>::Add(var<u1>, !!T0)
0xed92  ldloc.0
0xed93  call     void Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::SweepReleasedMapsIfNecessary(class Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection currentGroup)
0xed98  leave.s  loc_EDA4
0xed9a  ldloc.3
0xed9b  brfalse.s loc_EDA3
0xed9d  ldloc.2
0xed9e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xeda3  endfinally
0xeda4  ldloc.0
0xeda5  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::IncrementVersion()
0xedaa  pop
0xedab  ret
```
