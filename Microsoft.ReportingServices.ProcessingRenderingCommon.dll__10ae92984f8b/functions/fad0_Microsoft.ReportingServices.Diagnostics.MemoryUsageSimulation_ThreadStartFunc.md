# Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::ThreadStartFunc

- ea: `0xfad0`
- end: `0xfb55`
- name: `Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::ThreadStartFunc`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xfad0`
- `0x161b0`
- `0x161c0`

## string_xrefs

- `0xfb32`: `Simulator Enqueue Thread Hit Exception: `

## pseudocode

```c

```

## disassembly

```asm
0xfad0  ldc.i4   0x7530
0xfad5  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xfada  ldc.i4.1
0xfadb  newarr   SimpleMethod
0xfae0  dup
0xfae1  ldc.i4.0
0xfae2  ldarg.0
0xfae3  ldftn    instance void Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::RunMemoryRequest()
0xfae9  newobj   instance void SimpleMethod::.ctor(object object, native int method)
0xfaee  stelem.ref
0xfaef  stloc.0
0xfaf0  br.s     loc_FB4A
0xfaf2  nop
0xfaf3  ldarg.0
0xfaf4  ldfld    class [mscorlib]System.Random Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::m_rand
0xfaf9  stloc.2
0xfafa  ldc.i4.0
0xfafb  stloc.3
0xfafc  ldloc.2
0xfafd  ldloca.s 3
0xfaff  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xfb04  ldloc.0
0xfb05  ldarg.0
0xfb06  ldfld    class [mscorlib]System.Random Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::m_rand
0xfb0b  ldloc.0
0xfb0c  ldlen
0xfb0d  conv.i4
0xfb0e  callvirt instance int32 [mscorlib]System.Random::Next(int32)
0xfb13  ldelem.ref
0xfb14  stloc.1
0xfb15  leave.s  loc_FB21
0xfb17  ldloc.3
0xfb18  brfalse.s loc_FB20
0xfb1a  ldloc.2
0xfb1b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xfb20  endfinally
0xfb21  ldloc.1
0xfb22  callvirt instance void SimpleMethod::Invoke()
0xfb27  ldc.i4.s 0x64
0xfb29  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xfb2e  leave.s  loc_FB4A
0xfb30  stloc.s  4
0xfb32  ldstr    aSimulatorEnque// "Simulator Enqueue Thread Hit Exception:"...
0xfb37  ldloc.s  4
0xfb39  callvirt instance string [mscorlib]System.Object::ToString()
0xfb3e  call     string [mscorlib]System.String::Concat(string, string)
0xfb43  call     void [mscorlib]System.Console::WriteLine(string)
0xfb48  leave.s  loc_FB4A
0xfb4a  ldarg.0
0xfb4b  volatile.
0xfb4d  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.ReportingServices.Diagnostics.MemoryUsageSimulation::m_stop
0xfb52  brfalse.s loc_FAF2
0xfb54  ret
```
