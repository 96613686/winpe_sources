# Microsoft.ReportingServices.Library.CachedSystemProperties::get_Cache

- ea: `0x870`
- end: `0x8a5`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_Cache`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa0`

## callees

- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x870  ldsfld   object Microsoft.ReportingServices.Library.CachedSystemProperties::m_lockObj
0x875  stloc.0
0x876  ldc.i4.0
0x877  stloc.1
0x878  ldloc.0
0x879  ldloca.s 1
0x87b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x880  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.CachedSystemProperties::m_Cache
0x885  brtrue.s loc_891
0x887  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x88c  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.CachedSystemProperties::m_Cache
0x891  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.CachedSystemProperties::m_Cache
0x896  stloc.2
0x897  leave.s  loc_8A3
0x899  ldloc.1
0x89a  brfalse.s loc_8A2
0x89c  ldloc.0
0x89d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8a2  endfinally
0x8a3  ldloc.2
0x8a4  ret
```
