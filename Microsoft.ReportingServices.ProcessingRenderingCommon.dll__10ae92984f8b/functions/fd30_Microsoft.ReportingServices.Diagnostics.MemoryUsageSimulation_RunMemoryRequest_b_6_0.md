# Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::<RunMemoryRequest>b__6_0

- ea: `0xfd30`
- end: `0xfd61`
- name: `Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::<RunMemoryRequest>b__6_0`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xfd30`
- `0xfe10`
- `0xffb0`
- `0x10030`

## string_xrefs

- `0xfd3d`: `Simulator worker thread hit exception: `

## pseudocode

```c

```

## disassembly

```asm
0xfd30  newobj   instance void Microsoft.ReportingServices.Diagnostics.MemoryRequest::.ctor()
0xfd35  callvirt instance void Microsoft.ReportingServices.Diagnostics.MemoryRequest::DoWork()
0xfd3a  leave.s  loc_FD60
0xfd3c  stloc.0
0xfd3d  ldstr    aSimulatorWorke// "Simulator worker thread hit exception: "
0xfd42  ldloc.0
0xfd43  callvirt instance string [mscorlib]System.Object::ToString()
0xfd48  call     string [mscorlib]System.String::Concat(string, string)
0xfd4d  call     void [mscorlib]System.Console::WriteLine(string)
0xfd52  leave.s  loc_FD60
0xfd54  ldarg.0
0xfd55  ldfld    class Microsoft.ReportingServices.Diagnostics.ManagedSemaphore Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::m_workerSemaphore
0xfd5a  callvirt instance void Microsoft.ReportingServices.Diagnostics.ManagedSemaphore::Release()
0xfd5f  endfinally
0xfd60  ret
```
