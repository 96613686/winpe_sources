# System.Windows.Xps.XpsDocumentWriter::WriteAsync_1

- ea: `0xb780`
- end: `0xb7b2`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_1`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb740`

## callees

- `0xb780`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb780  ldarg.0
0xb781  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb786  ldarg.2
0xb787  ldnull
0xb788  bne.un.s loc_B78D
0xb78a  ldc.i4.0
0xb78b  br.s     loc_B78E
0xb78d  ldc.i4.1
0xb78e  stloc.0
0xb78f  ldarg.0
0xb790  ldc.i4.0
0xb791  ldc.i4.1
0xb792  ldloc.0
0xb793  ldarg.2
0xb794  ldc.i4.3
0xb795  ldc.i4.0
0xb796  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb79b  ldc.i4.1
0xb79c  bne.un.s loc_B7B1
0xb79e  ldarg.0
0xb79f  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb7a4  ldarg.1
0xb7a5  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb7aa  ldarg.0
0xb7ab  ldc.i4.0
0xb7ac  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb7b1  ret
```
