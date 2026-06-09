# Microsoft.ReportingServices.Portal.Services.TelemetryService::IsThisVirtualMachine

- ea: `0xa730`
- end: `0xa7a8`
- name: `Microsoft.ReportingServices.Portal.Services.TelemetryService::IsThisVirtualMachine`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa190`

## callees

- `0xa730`

## string_xrefs

- `0xa730`: `SELECT * FROM Win32_ComputerSystem`

## pseudocode

```c

```

## disassembly

```asm
0xa730  ldstr    aSelectFromWin3// "SELECT * FROM Win32_ComputerSystem"
0xa735  newobj   instance void [System.Management]System.Management.ManagementObjectSearcher::.ctor(string)
0xa73a  ldc.i4.0
0xa73b  stloc.0
0xa73c  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementObjectSearcher::Get()
0xa741  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0xa746  stloc.1
0xa747  br.s     loc_A792
0xa749  ldloc.1
0xa74a  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0xa74f  castclass [System.Management]System.Management.ManagementObject
0xa754  stloc.2
0xa755  ldloc.2
0xa756  ldstr    aModel// "Model"
0xa75b  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0xa760  callvirt instance string [mscorlib]System.Object::ToString()
0xa765  ldstr    aVirtualMachine// "Virtual Machine"
0xa76a  call     int32 [mscorlib]System.String::Compare(string, string)
0xa76f  brfalse.s loc_A790
0xa771  ldloc.2
0xa772  ldstr    aModel// "Model"
0xa777  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0xa77c  callvirt instance string [mscorlib]System.Object::ToString()
0xa781  ldstr    aVmwareVirtualP// "VMware Virtual Platform"
0xa786  call     int32 [mscorlib]System.String::Compare(string, string)
0xa78b  ldc.i4.0
0xa78c  ceq
0xa78e  br.s     loc_A791
0xa790  ldc.i4.1
0xa791  stloc.0
0xa792  ldloc.1
0xa793  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0xa798  brtrue.s loc_A749
0xa79a  leave.s  loc_A7A6
0xa79c  ldloc.1
0xa79d  brfalse.s loc_A7A5
0xa79f  ldloc.1
0xa7a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7a5  endfinally
0xa7a6  ldloc.0
0xa7a7  ret
```
