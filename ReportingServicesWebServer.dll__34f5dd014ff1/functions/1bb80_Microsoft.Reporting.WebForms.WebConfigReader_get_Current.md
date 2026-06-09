# Microsoft.Reporting.WebForms.WebConfigReader::get_Current

- ea: `0x1bb80`
- end: `0x1bbb5`
- name: `Microsoft.Reporting.WebForms.WebConfigReader::get_Current`
- size: `53`
- prototype: ``
- caller_count: `52`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4100`
- `0x4110`
- `0x4120`
- `0x4130`
- `0x4140`
- `0x4170`
- `0x41a0`
- `0x41d0`
- `0x4200`
- `0x4230`
- `0x4260`
- `0x4290`
- `0x42c0`
- `0x42f0`
- `0x4320`
- `0x4350`
- `0x4380`
- `0x43b0`
- `0x43e0`
- `0x4410`
- `0x4440`
- `0x4470`
- `0x44a0`
- `0x44d0`
- `0x4500`
- `0x4530`
- `0x4560`
- `0x4590`
- `0x45c0`
- `0x45f0`
- `0x4620`
- `0x4650`
- `0x4680`
- `0x46b0`
- `0x46e0`
- `0x4710`
- `0x4740`
- `0x4770`
- `0x47a0`
- `0x47d0`
- `0x4800`
- `0x4830`
- `0x4860`
- `0x4890`
- `0x48c0`
- `0x48f0`
- `0x4920`
- `0x9420`
- `0x11630`
- `0x11a20`

## callees

- `0x1bb30`
- `0x1bb80`

## pseudocode

```c

```

## disassembly

```asm
0x1bb80  ldsfld   object Microsoft.Reporting.WebForms.WebConfigReader::m_lockObject
0x1bb85  stloc.0
0x1bb86  ldc.i4.0
0x1bb87  stloc.1
0x1bb88  ldloc.0
0x1bb89  ldloca.s 1
0x1bb8b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1bb90  ldsfld   class Microsoft.Reporting.WebForms.WebConfigReader Microsoft.Reporting.WebForms.WebConfigReader::m_theInstance
0x1bb95  brtrue.s loc_1BBA1
0x1bb97  newobj   instance void Microsoft.Reporting.WebForms.WebConfigReader::.ctor()
0x1bb9c  stsfld   class Microsoft.Reporting.WebForms.WebConfigReader Microsoft.Reporting.WebForms.WebConfigReader::m_theInstance
0x1bba1  ldsfld   class Microsoft.Reporting.WebForms.WebConfigReader Microsoft.Reporting.WebForms.WebConfigReader::m_theInstance
0x1bba6  stloc.2
0x1bba7  leave.s  loc_1BBB3
0x1bba9  ldloc.1
0x1bbaa  brfalse.s loc_1BBB2
0x1bbac  ldloc.0
0x1bbad  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1bbb2  endfinally
0x1bbb3  ldloc.2
0x1bbb4  ret
```
