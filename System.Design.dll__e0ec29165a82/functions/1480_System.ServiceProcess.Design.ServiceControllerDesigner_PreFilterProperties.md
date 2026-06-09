# System.ServiceProcess.Design.ServiceControllerDesigner::PreFilterProperties

- ea: `0x1480`
- end: `0x14fe`
- name: `System.ServiceProcess.Design.ServiceControllerDesigner::PreFilterProperties`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x58fe0`
- `0x5d760`

## string_xrefs

- `0x1490`: `ServiceName`
- `0x14c7`: `DependentServices`
- `0x14cf`: `ServicesDependedOn`
- `0x14df`: `ServiceType`

## pseudocode

```c

```

## disassembly

```asm
0x1480  ldarg.0
0x1481  ldarg.1
0x1482  call     instance void System.ComponentModel.Design.ComponentDesigner::PreFilterProperties(class [mscorlib]System.Collections.IDictionary properties)
0x1487  ldarg.1
0x1488  ldc.i4.2
0x1489  newarr   [mscorlib]System.String
0x148e  dup
0x148f  ldc.i4.0
0x1490  ldstr    aServicename// "ServiceName"
0x1495  stelem.ref
0x1496  dup
0x1497  ldc.i4.1
0x1498  ldstr    aDisplayname// "DisplayName"
0x149d  stelem.ref
0x149e  ldc.i4.s 9
0x14a0  newarr   [mscorlib]System.String
0x14a5  dup
0x14a6  ldc.i4.0
0x14a7  ldstr    aCanpauseandcon// "CanPauseAndContinue"
0x14ac  stelem.ref
0x14ad  dup
0x14ae  ldc.i4.1
0x14af  ldstr    aCanshutdown// "CanShutdown"
0x14b4  stelem.ref
0x14b5  dup
0x14b6  ldc.i4.2
0x14b7  ldstr    aCanstop// "CanStop"
0x14bc  stelem.ref
0x14bd  dup
0x14be  ldc.i4.3
0x14bf  ldstr    aDisplayname// "DisplayName"
0x14c4  stelem.ref
0x14c5  dup
0x14c6  ldc.i4.4
0x14c7  ldstr    aDependentservi// "DependentServices"
0x14cc  stelem.ref
0x14cd  dup
0x14ce  ldc.i4.5
0x14cf  ldstr    aServicesdepend// "ServicesDependedOn"
0x14d4  stelem.ref
0x14d5  dup
0x14d6  ldc.i4.6
0x14d7  ldstr    aStatus// "Status"
0x14dc  stelem.ref
0x14dd  dup
0x14de  ldc.i4.7
0x14df  ldstr    aServicetype// "ServiceType"
0x14e4  stelem.ref
0x14e5  dup
0x14e6  ldc.i4.8
0x14e7  ldstr    aMachinename// "MachineName"
0x14ec  stelem.ref
0x14ed  ldc.i4.s 9
0x14ef  newarr   [mscorlib]System.Boolean
0x14f4  dup
0x14f5  ldc.i4.8
0x14f6  ldc.i4.1
0x14f7  stelem.i1
0x14f8  call     void System.ComponentModel.Design.RuntimeComponentFilter::FilterProperties(class [mscorlib]System.Collections.IDictionary properties, class [mscorlib]System.Collections.ICollection makeReadWrite, class [mscorlib]System.Collections.ICollection makeBrowsable, bool[] browsableSettings)
0x14fd  ret
```
