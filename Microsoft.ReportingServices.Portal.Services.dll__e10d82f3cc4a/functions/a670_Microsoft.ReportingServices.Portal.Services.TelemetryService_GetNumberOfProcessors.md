# Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfProcessors

- ea: `0xa670`
- end: `0xa6c3`
- name: `Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfProcessors`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa190`

## callees

- `0xa670`

## string_xrefs

- `0xa670`: `SELECT * FROM Win32_ComputerSystem`

## pseudocode

```c

```

## disassembly

```asm
0xa670  ldstr    aSelectFromWin3// "SELECT * FROM Win32_ComputerSystem"
0xa675  newobj   instance void [System.Management]System.Management.ManagementObjectSearcher::.ctor(string)
0xa67a  ldc.i4.0
0xa67b  stloc.0
0xa67c  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementObjectSearcher::Get()
0xa681  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0xa686  stloc.1
0xa687  br.s     loc_A6AD
0xa689  ldloc.1
0xa68a  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0xa68f  castclass [System.Management]System.Management.ManagementObject
0xa694  stloc.2
0xa695  ldloc.0
0xa696  ldloc.2
0xa697  ldstr    aNumberofproces// "NumberOfProcessors"
0xa69c  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0xa6a1  callvirt instance string [mscorlib]System.Object::ToString()
0xa6a6  call     int32 [mscorlib]System.Int32::Parse(string)
0xa6ab  add
0xa6ac  stloc.0
0xa6ad  ldloc.1
0xa6ae  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0xa6b3  brtrue.s loc_A689
0xa6b5  leave.s  loc_A6C1
0xa6b7  ldloc.1
0xa6b8  brfalse.s loc_A6C0
0xa6ba  ldloc.1
0xa6bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6c0  endfinally
0xa6c1  ldloc.0
0xa6c2  ret
```
